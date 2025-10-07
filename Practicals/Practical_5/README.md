# Practical 5 - TestContainers Integration Testing

Implementation of integration testing using TestContainers for PostgreSQL and Redis in Go.

## Implementation

Complete implementation available in separate repository: [SWE302_p5](https://github.com/KeldenPDorji/SWE302_p5)

## Overview

This practical demonstrates:
- Integration testing with TestContainers
- PostgreSQL database testing
- Redis caching integration
- Full CRUD operations with advanced queries
- Transaction testing and isolation
- Multi-container setup

## Prerequisites

- Go 1.21 or higher
- Docker Desktop running
- ~500MB disk space for Docker images

## Quick Start

```bash
# Clone the repository
git clone https://github.com/KeldenPDorji/SWE302_p5.git
cd SWE302_p5

# Download dependencies
go mod download

# Run all tests
go test ./... -v
```

## Project Structure

```
SWE302_p5/
├── models/
│   └── user.go                          # User data model
├── repository/
│   ├── user_repository.go               # Basic CRUD operations
│   ├── user_repository_test.go          # Integration tests (Exercises 1-4)
│   ├── cached_user_repository.go        # Redis caching layer
│   └── cached_user_repository_test.go   # Multi-container tests (Exercise 5)
├── migrations/
│   └── init.sql                         # Database schema
├── go.mod                               # Dependencies
└── README.md                            # Project documentation
```

## Exercises Implemented

### Exercise 1-2: Basic CRUD Operations
- User retrieval by ID and email
- User creation, update, and deletion
- User listing functionality

### Exercise 3: Advanced Queries
- Pattern matching with ILIKE
- User counting
- Date-based filtering

### Exercise 4: Transaction Testing
- Atomic batch operations
- Complex transaction handling
- Rollback behavior verification
- Concurrent access testing

### Exercise 5: Multi-Container Testing
- Cache hit/miss scenarios
- Cache invalidation testing
- TTL verification

## Test Execution

```bash
# Run all tests
go test ./... -v

# Run with coverage
go test -cover ./repository

# Run specific test
go test ./repository -run TestGetByID -v
```

## Key Features

- **Real Database Testing**: Uses actual PostgreSQL and Redis containers
- **Automatic Container Management**: TestContainers handles lifecycle
- **Test Isolation**: Clean state for each test
- **Production-Like Environment**: Same databases as production

## Technical Implementation

- **Unified TestMain**: Single setup for PostgreSQL and Redis containers
- **Interface-Based Design**: DBExecutor interface for flexibility
- **Proper Error Handling**: Comprehensive error messages
- **Clean Architecture**: Separation of concerns

## Learning Outcomes

1. Integration testing best practices
2. Container-based testing strategies
3. Database transaction management
4. Cache integration patterns
5. Go testing frameworks

---

