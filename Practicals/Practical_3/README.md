# Practical 3: Software Testing & Quality Assurance
## Specification-Based Testing in Go

This project demonstrates comprehensive specification-based testing techniques including Equivalence Partitioning, Boundary Value Analysis, and Decision Table Testing.

## Files Structure

- `shipping.go` - Original shipping calculator implementation
- `shipping_test.go` - Comprehensive tests for original shipping calculator
- `shipping_v2.go` - Updated shipping calculator with tiered pricing and insurance
- `shipping_v2_test.go` - Comprehensive tests for updated shipping calculator
- `go.mod` - Go module definition

## Parameter Ranges Documentation

### Original Shipping Calculator (`CalculateShippingFee`)
**Function Signature:** `CalculateShippingFee(weight float64, zone string) (float64, error)`

| Parameter | Data Type | Test Range | Valid Business Range | Invalid Examples | Valid Examples |
|-----------|-----------|------------|---------------------|------------------|----------------|
| `weight` | `float64` | (-∞, +∞) | (0, 50] kg | -10, -5, 0, 50.1, 100 | 0.1, 5.0, 25.5, 50.0 |
| `zone` | `string` | Any string | {"Domestic", "International", "Express"} | "", "domestic", "Local", "DOMESTIC" | "Domestic", "International", "Express" |

### Updated Shipping Calculator V2 (`CalculateShippingFeeV2`)
**Function Signature:** `CalculateShippingFeeV2(weight float64, zone string, insured bool) (float64, error)`

| Parameter | Data Type | Test Range | Valid Business Range | Invalid Examples | Valid Examples |
|-----------|-----------|------------|---------------------|------------------|----------------|
| `weight` | `float64` | (-∞, +∞) | (0, 50] kg with tiers:<br/>• (0, 10] = Standard<br/>• (10, 50] = Heavy | -10, 0, 50.1, 75 | 0.1, 5.0, 10.0, 10.1, 25.0, 50.0 |
| `zone` | `string` | Any string | {"Domestic", "International", "Express"} | "", "domestic", "Local" | "Domestic", "International", "Express" |
| `insured` | `bool` | {true, false} | {true, false} | N/A (boolean type) | true, false |

### Range-Based Test Strategy

**Why Parameter Ranges Matter:**
1. **Comprehensive Coverage**: Testing both valid and invalid ranges ensures robust validation
2. **Edge Case Detection**: Boundary values often reveal off-by-one errors and logic flaws
3. **Input Validation**: Confirms the function properly rejects invalid inputs
4. **Business Logic Verification**: Ensures calculations work correctly across all valid scenarios

## Part 1: Analysis of Test Cases Design

### Equivalence Partitioning Analysis

#### For shipping_v2.go (Updated Requirements):

**Weight Input Partitions:**
- **P1: Invalid Weight - Too Low** (weight ≤ 0)
  - Examples: -10, -5, 0
  - Expected: Error "invalid weight"
  - Rationale: The specification states weight must be greater than 0
  
- **P2: Valid Weight - Standard Tier** (0 < weight ≤ 10)
  - Examples: 0.1, 5.0, 10.0
  - Expected: Base fee only (no heavy surcharge)
  - Rationale: Packages 10kg or less are considered "Standard" with no additional surcharge
  
- **P3: Valid Weight - Heavy Tier** (10 < weight ≤ 50)
  - Examples: 10.1, 25.0, 50.0
  - Expected: Base fee + $7.50 heavy surcharge
  - Rationale: Packages over 10kg get a fixed $7.50 surcharge
  
- **P4: Invalid Weight - Too High** (weight > 50)
  - Examples: 50.1, 75.0, 100.0
  - Expected: Error "invalid weight"
  - Rationale: Maximum weight limit is 50kg per specification

**Zone Input Partitions:**
- **P5: Valid Zones**
  - Values: "Domestic", "International", "Express"
  - Expected: Corresponding base fees ($5, $20, $30 respectively)
  - Rationale: These are the only three valid zone strings per specification
  
- **P6: Invalid Zones**
  - Examples: "", "domestic" (lowercase), "Local", "Unknown"
  - Expected: Error "invalid zone: [value]"
  - Rationale: Any string not exactly matching the valid zones is invalid

**Insurance Input Partitions:**
- **P7: Insurance Enabled** (insured = true)
  - Expected: Additional 1.5% of (base fee + surcharge) added to total
  - Rationale: When insured is true, insurance cost is calculated as specified
  
- **P8: Insurance Disabled** (insured = false)
  - Expected: No additional insurance cost
  - Rationale: When insured is false, no insurance calculation is performed

### Boundary Value Analysis

#### Weight Boundaries:

**Lower Boundary (around 0):**
- **0** - Last invalid value (should error)
- **0.1** - First valid value (should succeed with standard tier)
- Rationale: The specification uses "greater than 0", so 0 is invalid but any positive value is valid

**Mid Boundary (around 10kg - Standard/Heavy threshold):**
- **10.0** - Last value in standard tier (no surcharge)
- **10.1** - First value in heavy tier (gets $7.50 surcharge)
- Rationale: This is the critical threshold where the heavy surcharge begins

**Upper Boundary (around 50kg):**
- **50.0** - Last valid weight (should succeed)
- **50.1** - First invalid weight (should error)
- Rationale: The specification states "no more than 50 kg", so 50 is valid but 50.1 is not

#### Why These Boundaries Matter:

1. **Off-by-one errors**: Common programming mistakes occur at boundaries (using >= instead of >, etc.)
2. **Business logic transitions**: The 10kg boundary is where pricing logic changes significantly
3. **Input validation edges**: The 0 and 50 boundaries test the validation logic thoroughly

### Decision Table Testing

The decision table systematically covers all combinations of:
- Weight validity (Valid/Invalid)
- Weight tier (Standard/Heavy) - when valid
- Zone validity (Valid/Invalid) 
- Zone type (Domestic/International/Express) - when valid
- Insurance status (True/False)

This ensures no combination of business rules is missed and validates that the function behaves correctly under all specified scenarios.

## Test Implementation Strategy

### Table-Driven Tests
All tests use Go's table-driven testing pattern for several advantages:
- **Scalability**: Easy to add new test cases
- **Maintainability**: Clear separation of test data and test logic
- **Readability**: Each test case is self-documenting
- **Comprehensive coverage**: Systematic approach ensures no scenarios are missed

### Error Validation
Tests validate both:
- **Error presence**: When errors should occur
- **Error content**: Ensuring correct error messages are returned
- **No false positives**: Ensuring valid inputs don't trigger errors

### Floating Point Precision
For fee calculations, tests use a small tolerance (0.0001) to handle floating-point precision issues, which is important for financial calculations.

## Running the Tests

```bash
# Run all tests
go test -v

# Run tests with coverage
go test -cover -v

# Run only the original shipping tests
go test -run TestCalculateShippingFee -v

# Run only the V2 shipping tests  
go test -run TestCalculateShippingFeeV2 -v
```

## Demo Screenshots

![alt text](<Screenshot 2025-09-09 at 9.17.10 PM.png>)

## Key Testing Principles Demonstrated

1. **Black-box testing**: Tests are designed from specifications, not implementation
2. **Systematic coverage**: Using formal techniques ensures comprehensive test coverage
3. **Edge case focus**: Boundary value analysis finds bugs that often hide at edge conditions
4. **Business rule validation**: Decision tables ensure all business logic combinations are tested
5. **Error handling**: Comprehensive validation of both success and failure scenarios

This approach results in robust, maintainable tests that will catch regressions and validate that the implementation correctly follows the business requirements.
