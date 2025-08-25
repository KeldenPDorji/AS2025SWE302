# Go CRUD Testing Assignment

This project demonstrates comprehensive unit testing for a Go HTTP se1. Reset state
2. Create mock request
3. Execute handler
4. Verify response status and body
5. Check side effects (state changes)

## Demo Screenshots

### Terminal Test Execution
The following screenshot demonstrates the successful execution of all test cases with verbose output:

![alt text](<Screenshot 2025-08-25 at 12.01.23 PM.png>)

**Key highlights from terminal output:**
- All 13 test cases pass successfully
- Coverage report shows 85.7% statement coverage
- Tests include both success scenarios and comprehensive error handling

### Visual Code Coverage Report
The HTML coverage report provides a detailed, line-by-line view of test coverage:

![alt text](<Screenshot 2025-08-25 at 11.58.30 AM.png>) 

**Coverage report features:**
- **Green highlighting**: Indicates tested code paths
- **Red highlighting**: Shows untested lines (opportunities for improvement)
- **Detailed metrics**: Percentage breakdown by function and file
- **Interactive navigation**: Click-through functionality for source exploration

## Learning Outcomes

This assignment demonstrates mastery of:
- **Unit Testing Best Practices**: Writing comprehensive tests for HTTP handlers
- **Go Testing Ecosystem**: Leveraging `testing`, `net/http/httptest`, and coverage tools
- **Test Coverage Analysis**: Understanding and interpreting coverage metrics
- **Error Scenario Testing**: Validating both success and failure conditions
- **Concurrent Programming**: Ensuring thread-safe operations with mutexes
- **API Testing Methodology**: Simulating HTTP requests and validating responses
- **Test Organization**: Structuring tests with subtests and helper functions
- **Documentation**: Creating clear, comprehensive project documentation

## Assignment Completion Summary

✅ **Project Setup**: Go module with proper dependency management  
✅ **CRUD Implementation**: Complete REST API with all five operations  
✅ **Comprehensive Testing**: 13 test cases covering success and error scenarios  
✅ **High Coverage**: 85.7% statement coverage exceeding industry standards  
✅ **Documentation**: Detailed README with screenshots and explanations  
✅ **Code Quality**: Clean, well-structured, and maintainable codetions, as part of the Software Testing & Quality Assurance practical.

## Project Structure

```
go-crud-testing/
├── go.mod              # Go module definition
├── main.go             # Server entry point
├── handlers.go         # HTTP handlers for CRUD operations
├── handlers_test.go    # Comprehensive unit tests
├── coverage.out        # Test coverage profile
└── README.md          # This file
```

## Features

### API Endpoints
- `GET /users` - Get all users
- `POST /users` - Create a new user
- `GET /users/{id}` - Get a specific user by ID
- `PUT /users/{id}` - Update a user by ID
- `DELETE /users/{id}` - Delete a user by ID

### Test Coverage
The test suite includes comprehensive coverage for:

1. **Create User Handler**
   - Successful user creation
   - Invalid JSON handling

2. **Get All Users Handler**
   - Users exist scenario
   - Empty user list scenario

3. **Get User Handler**
   - User found
   - User not found
   - Invalid ID format

4. **Update User Handler**
   - Successful update
   - User not found
   - Invalid ID format
   - Invalid JSON handling

5. **Delete User Handler**
   - Successful deletion
   - User not found
   - Invalid ID format

## Running the Project

### Install Dependencies
```bash
go mod tidy
```

### Run the Server
```bash
go run .
```
The server will start on `http://localhost:3000`

### Run Tests
```bash
# Run all tests
go test -v

# Run tests with coverage
go test -v -cover

# Generate coverage profile
go test -coverprofile=coverage.out

# Generate HTML coverage report
go tool cover -html=coverage.out
```

## Test Results

Current test coverage: **85.7%** of statements

All tests pass successfully, demonstrating:
- Proper HTTP status code validation
- JSON request/response handling
- Error condition testing
- State management verification

## Testing Approach

The tests use Go's built-in testing framework with:
- `net/http/httptest` for creating mock HTTP requests and responses
- `github.com/go-chi/chi/v5` router for URL parameter extraction
- JSON encoding/decoding for request/response bodies
- Comprehensive edge case testing

Each test follows the pattern:
1. Reset state
2. Create mock request
3. Execute handler
4. Verify response status and body
5. Check side effects (state changes)









