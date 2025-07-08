# 🚀 C# DevSecOps Pipeline

## Overview

This project demonstrates an **end-to-end DevSecOps pipeline for a .NET/C# application**, showcasing practical integration of security and quality checks within the CI/CD workflow using **GitHub Actions**.

It automates:

* **SAST (Static Application Security Testing)** with **SonarCloud**
* **SCA (Software Composition Analysis)** with **Snyk**
* **DAST (Dynamic Application Security Testing)** with **OWASP ZAP**

The pipeline is designed to **shift security left**, ensuring vulnerabilities and code issues are detected early while maintaining developer velocity in a modern DevOps environment.

---

## Key Features

✅ Automated **build and test** on push and PR events
✅ **SonarCloud integration** for code quality and vulnerability detection (SAST)
✅ **Snyk integration** for dependency vulnerability scanning (SCA)
✅ **OWASP ZAP integration** for dynamic application scanning (DAST)
✅ Modular, reusable **GitHub Actions workflow**
✅ Practical reference for **DevSecOps in .NET ecosystems**

---

## Pipeline Workflow

### 1️⃣ SAST - SonarCloud Analysis

* Runs on `windows-latest` for .NET build compatibility.
* Uses `dotnet-sonarscanner` to:

  * Analyse the codebase for vulnerabilities, bugs, and code smells.
  * Enforce code quality gates before merging.
* Requires `SONAR_TOKEN` secret in GitHub.

### 2️⃣ SCA - Snyk Dependency Scanning

* Uses `snyk/actions/dotnet` to scan for vulnerable dependencies.
* Provides vulnerability reports directly in the GitHub Actions output.
* Requires `SNYK_TOKEN` secret in GitHub.

### 3️⃣ DAST - OWASP ZAP Baseline Scan

* Uses `zaproxy/action-baseline` to perform a baseline scan against a test target.
* Demonstrates dynamic scanning capabilities that can be adapted to real-world endpoints.

---

## Project Structure

```
.github/workflows/
└── devsecops-workflow.yaml        # GitHub Actions pipeline

SomeConsoleApplication/           # Sample C# console app
SomeConsoleApplicationTest/       # Sample unit tests
LICENSE
README.md
SomeConsoleApplication.sln
packages.config
```

---

## Setup

### Prerequisites

✅ GitHub repository with this project structure
✅ GitHub Actions enabled
✅ Secrets:

* `SONAR_TOKEN` for SonarCloud authentication.
* `SNYK_TOKEN` for Snyk authentication.

---

### Running the Pipeline

The workflow is triggered automatically:

* On **pushes to `master`**.
* On **Pull Requests (opened, synchronised, reopened)**.

You can monitor results under the **Actions** tab of your GitHub repository.

---

## Security Approach

✅ **Shift-left security:** Vulnerabilities are detected early in the SDLC.
✅ **Automated gates:** PRs can be blocked based on scan results if desired.
✅ **Integrated scanning:** No manual intervention needed post-setup.

---

## Author

**Diler M**
[LinkedIn](https://www.linkedin.com/in/diler-m-5b9756121/) | [GitHub](https://github.com/Diler-M)
