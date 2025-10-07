# Practical 4: DevSecOps Pipeline Implementation with Snyk SAST Integration

## 📊 Technology Stack & Badges
![Java](https://img.shields.io/badge/Java-17-red?style=flat-square&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.4.9-brightgreen?style=flat-square&logo=spring-boot)
![GitHub Actions](https://img.shields.io/badge/CI%2FCD-GitHub%20Actions-2088FF?style=flat-square&logo=github-actions)
![Snyk](https://img.shields.io/badge/Security-Snyk-4C2B5E?style=flat-square&logo=snyk)
![DevSecOps](https://img.shields.io/badge/DevSecOps-Enabled-success?style=flat-square)

## 📋 Project Summary

This repository contains a **Spring Boot CI/CD demonstration project** that showcases the integration of **Static Application Security Testing (SAST)** with **Snyk** in GitHub Actions workflows. The project implements modern DevSecOps practices with automated security scanning and vulnerability management.

## 🔗 **[View Full Project Repository →](https://github.com/KeldenPDorji/cicd-demo)**

## 🎯 What This Project Demonstrates

### **Core Technologies**
- **Java 17** with Spring Boot 3.4.9
- **Maven** for dependency management
- **GitHub Actions** for CI/CD automation
- **Snyk** for security vulnerability scanning
- **Docker** with multi-stage builds
- **JaCoCo** for code coverage reporting

### **Key Features Implemented**
- ✅ Automated security scanning with Snyk
- ✅ SARIF integration for GitHub Security tab
- ✅ Vulnerability management with custom policies
- ✅ Multi-stage Docker builds for security
- ✅ Comprehensive CI/CD pipeline with security-first approach

### **API Endpoints**
| Endpoint | Description |
|----------|-------------|
| `/` | Health check endpoint |
| `/version` | Application version info |
| `/nations` | Random nation data (JSON) |
| `/currencies` | Random currency data (JSON) |

---

## 🏗️ Pipeline Architecture

```
Developer Commits → GitHub Actions → Snyk Security Scan → SARIF Reports → GitHub Security Tab
      ↓                   ↓                 ↓                    ↓
   Git Push          Build & Test      Vulnerability        Security 
                                      Detection            Monitoring
```

---

## 📚 Learning Objectives (NUS-ISS Practical 4)

This project was developed as part of the **NUS-ISS EPAT CI/CD Workshop** focusing on:

- **Static Application Security Testing (SAST)** implementation
- **DevSecOps** pipeline integration 
- **Automated vulnerability management**
- **Security reporting and monitoring**
- **Industry best practices** for secure development

---

## 🚀 Quick Access

### **Repository Links**
- 🏠 **[Main Repository](https://github.com/KeldenPDorji/cicd-demo)** - Complete project with full documentation
- 📖 **[README](https://github.com/KeldenPDorji/cicd-demo#readme)** - Comprehensive setup and usage guide
- 🔒 **[Security](https://github.com/KeldenPDorji/cicd-demo/security)** - GitHub Security tab with SARIF reports
- ⚡ **[Actions](https://github.com/KeldenPDorji/cicd-demo/actions)** - CI/CD pipeline execution history

### **Key Files**
- 📄 **[GitHub Workflow](https://github.com/KeldenPDorji/cicd-demo/blob/master/.github/workflows/maven.yml)** - CI/CD pipeline configuration
- 🔧 **[Maven POM](https://github.com/KeldenPDorji/cicd-demo/blob/master/pom.xml)** - Project dependencies and build config
- 🛡️ **[Snyk Config](https://github.com/KeldenPDorji/cicd-demo/blob/master/.snyk)** - Security scanning configuration
- 🐳 **[Dockerfile](https://github.com/KeldenPDorji/cicd-demo/blob/master/dockerfile)** - Multi-stage container build

---

## 🔍 Snyk Security Dashboard Overview
![Snyk Security Testing Dashboard](<Screenshot 2025-09-17 at 11.49.12 PM.png>)
*Figure 1: Snyk security testing dashboard showing comprehensive analysis of the cicd-demo project with zero vulnerabilities detected across code analysis, Maven configuration (pom.xml), and Docker setup (dockerfile)*

## 🚀 GitHub Actions CI/CD Pipeline Execution
![GitHub Actions Workflow Success](<Screenshot 2025-09-18 at 12.33.23 AM.png>)
*Figure 2: Successful execution of the "Enhanced CI/CD with Comprehensive Security" workflow (Run #13) demonstrating a complete DevSecOps pipeline with parallel security scanning, testing, container security, monitoring, and notification stages*

## 🔗 Related Resources

- 📖 **[Snyk Documentation](https://docs.snyk.io/)**
- 🔐 **[GitHub Actions Security](https://docs.github.com/en/actions/security-guides)**
- 🌟 **[Spring Boot Best Practices](https://spring.io/guides/gs/securing-web/)**
- 🚀 **[DevSecOps Guidelines](https://www.devsecops.org/)**

---

**For complete project details, setup instructions, and full documentation:**  
**👉 [Visit the Main Repository](https://github.com/KeldenPDorji/cicd-demo)**
