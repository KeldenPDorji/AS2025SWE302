# SWE302 - Practicals Repository

This repository contains practical assignments for **SWE302 - Software Testing** course (2025).

## 📚 Practical 4B: Dynamic Application Security Testing (DAST)

**Status:** ✅ Completed

Integration of OWASP ZAP dynamic security scanning in GitHub Actions CI/CD pipeline, demonstrating automated vulnerability testing on running applications with containerized security workflows.

### 🔗 [View Practical 4B Repository](https://github.com/KeldenPDorji/cicd-demo_sq)

---

### 📸 Project Screenshots

#### ZAP Baseline Scan Workflow
![ZAP Baseline Scan Workflow](https://raw.githubusercontent.com/KeldenPDorji/AS2025SWE302/main/Practicals/Practical_4B/image1.png)
*Successful Dynamic Application Security Testing scan integrated with GitHub Actions (3m 12s execution)*

#### Security Alerts Dashboard
![Security Alerts Summary](https://raw.githubusercontent.com/KeldenPDorji/AS2025SWE302/main/Practicals/Practical_4B/image2.png)
*Comprehensive vulnerability assessment: 0 High/Medium risks, 2 Low-risk findings, 5 informational alerts*

#### ZAP Scan Results Analysis
![ZAP Scan Results Dashboard](https://raw.githubusercontent.com/KeldenPDorji/AS2025SWE302/main/Practicals/Practical_4B/image3.png)
*Security Grade A achieved with strong overall security posture and detailed metrics*

---

### Key Features
- 🔍 **OWASP ZAP Integration** - Dynamic Application Security Testing with baseline and full scans
- 🐳 **Containerized Testing** - Docker-based consistent scanning environment
- ⚡ **Dual Scan Modes** - Fast baseline (~3 min) and comprehensive full scans (~30 min)
- 📊 **Security Reporting** - HTML reports with detailed vulnerability analysis
- 🛡️ **Custom Rules** - Tailored security checks via `.zap/rules.tsv` configuration
- 🔒 **Production Safety** - Passive scanning safe for live applications

### Technologies Used
- OWASP ZAP (DAST Scanner)
- GitHub Actions (CI/CD)
- Docker (Containerization)
- Java & Spring Boot
- Maven Build System
- Custom Security Rules

### Learning Outcomes
- Implementation of DAST in CI/CD pipelines
- Configuration of OWASP ZAP for automated security testing
- Containerization of applications for security scanning
- Analysis of dynamic security scan results and OWASP Top 10
- Security vulnerability remediation and header configuration
- Integration of DAST with SAST for comprehensive security coverage

---

**Student:** Kelden P. Dorji  
**Program:** Software Engineering  
**Year:** 2025
