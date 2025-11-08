# SWE302 - Practicals Repository

This repository contains practical assignments for **SWE302 - Software Testing** course (2025).

## 📚 Practical 5: TestContainers Integration Testing

**Status:** ✅ Completed

A comprehensive integration testing project demonstrating TestContainers implementation with PostgreSQL and Redis in Go, featuring real database testing with automatic container lifecycle management and multi-container orchestration.

### 🔗 [View Practical 5 Repository](https://github.com/KeldenPDorji/SWE302_p5)

---

### 📸 Project Screenshots

#### Test Execution - Container Initialization
![Test Execution](https://raw.githubusercontent.com/KeldenPDorji/SWE302_p5/main/image1.png)
*TestContainers initializing PostgreSQL and Redis containers with successful connections*

#### Complete Test Suite Results
![All Tests Passing](https://raw.githubusercontent.com/KeldenPDorji/SWE302_p5/main/image2.png)
*All 17 tests passing successfully covering CRUD, advanced queries, transactions, and caching*

#### Code Coverage Report
![Coverage Report](https://raw.githubusercontent.com/KeldenPDorji/SWE302_p5/main/image3.png)
*Achieved 83.3% code coverage across all repository tests*

---

### Key Features
- 🐳 **TestContainers Integration** - Real PostgreSQL and Redis containers (not mocks)
- 🗄️ **Full CRUD Operations** - Complete database interaction testing
- 🔄 **Advanced Transaction Testing** - Batch operations, rollback verification, concurrent access
- 🚀 **Multi-Container Setup** - PostgreSQL + Redis caching integration
- 📊 **High Test Coverage** - 83.3% code coverage with 17 comprehensive tests
- ⚙️ **Automatic Lifecycle** - Container setup and teardown management

### Technologies Used
- Go 1.21
- TestContainers
- PostgreSQL 15-alpine
- Redis 7-alpine
- Docker
- Go testing framework

### Learning Outcomes
- Integration testing with TestContainers framework
- Real database testing vs mocking strategies
- Multi-container orchestration and management
- Database transaction management and isolation
- Cache integration patterns and testing
- Production-like testing environment setup

---

**Student:** Kelden P. Dorji  
**Program:** Software Engineering  
**Year:** 2025
