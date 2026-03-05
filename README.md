# 🚀 Jenkins CI Pipeline with SonarQube, Quality Gate and GitHub Webhook

---

## 📌 Project Overview

This project demonstrates a **Continuous Integration (CI) pipeline using Jenkins integrated with GitHub and SonarQube**.

The application used in this pipeline is a **Spring Boot Employee API built with Maven**.

Jenkins automatically reads the **Jenkinsfile** from the GitHub repository and executes the pipeline whenever a developer pushes code to GitHub. This is achieved using a **GitHub Webhook trigger**, which automatically starts the Jenkins pipeline on every code change.

The pipeline performs **build, testing, static code analysis using SonarQube, Quality Gate validation, and artifact generation**.

This project demonstrates how **modern DevOps CI pipelines enforce code quality before generating deployable artifacts**.

---

## ⚙️ Tech Stack

* Java 17
* Spring Boot
* Maven
* Jenkins
* SonarQube
* Git
* GitHub
* GitHub Webhook

---

## 📂 Project Structure

```
jenkins-sonarqube-ci
│
├── Jenkinsfile
├── pom.xml
├── README.md
│
└── src
    └── main
        ├── java/com/example/employee
        │     ├── EmployeeApiApplication.java
        │     └── HelloController.java
        │
        └── resources
              └── application.properties
```

---

## ⚙️ Jenkins Pipeline Stages

The **Jenkinsfile** defines the following pipeline stages.

### 1️⃣ Checkout

Pulls the latest source code from the GitHub repository.

---

### 2️⃣ Build

```
mvn compile
```

Compiles the project source code.

---

### 3️⃣ Test

```
mvn test
```

Runs automated unit tests.

---

### 4️⃣ SonarQube Code Analysis

```
mvn sonar:sonar
```

Performs **static code analysis using SonarQube** and checks for:

* Bugs
* Vulnerabilities
* Code Smells
* Security issues

---

### 5️⃣ Quality Gate Validation

The **SonarQube Quality Gate** ensures that the code meets predefined quality standards such as:

* No critical vulnerabilities
* No major bugs
* Acceptable code duplication
* Successful test execution

If the **Quality Gate fails**, the CI pipeline can be configured to **stop the build process**.

---

### 6️⃣ Package

```
mvn package
```

Packages the application and generates the final **JAR artifact**.

---

## 🔄 CI Pipeline Workflow

```
Developer Push Code → GitHub
           ↓
       GitHub Webhook
           ↓
         Jenkins
           ↓
        Checkout
           ↓
          Build
           ↓
           Test
           ↓
    SonarQube Analysis
           ↓
        Quality Gate
           ↓
          Package
           ↓
       Artifact (.jar)
```

Whenever code is pushed to the GitHub repository, the **GitHub Webhook automatically triggers the Jenkins pipeline**, enabling fully automated Continuous Integration.

---

## 📊 SonarQube Analysis Result

After the pipeline execution, **SonarQube performs a complete code quality analysis**.

Example result:

```
Quality Gate: PASSED
Bugs: 0
Vulnerabilities: 0
Code Smells: 0
```

This ensures **only high-quality code proceeds through the CI pipeline**.

---

## 📦 Generated Artifact

After successful pipeline execution, Maven generates the build artifact:

```
target/employee-api-1.0.0.jar
```

This artifact can later be used for:

* Deployment to servers
* Docker containerization
* Cloud deployment (AWS, Kubernetes, etc.)

---

## ▶️ Run Application Manually (Optional)

### Build the project

```
mvn package
```

### Run the application

```
java -jar target/employee-api-1.0.0.jar
```

---

## 🌐 Example Endpoint

If the application is executed manually, it can be accessed at:

```
http://localhost:8080/
```

Example response:

```
Welcome to Employee API - Jenkins CI Pipeline with SonarQube!
```

---

## 🎯 What This Project Demonstrates

This project proves hands-on understanding of:

* Jenkins CI pipeline creation
* GitHub integration with Jenkins
* GitHub Webhook automation
* Pipeline as Code using Jenkinsfile
* Maven build lifecycle
* SonarQube static code analysis
* Quality Gate enforcement in CI pipelines
* Automated build, test, analysis, and packaging

---

## 💼 Why This Project Matters

This repository demonstrates **real-world DevOps practices**, including:

* Continuous Integration (CI)
* Automated code quality checks
* Static code analysis with SonarQube
* GitHub Webhook triggered pipelines
* Build automation
* Artifact generation for deployment pipelines

These are **core skills required for modern DevOps and cloud engineering roles**.

---

## 👨‍💻 Author

Developed as part of hands-on practice to strengthen **AWS, DevOps, CI/CD pipelines, and code quality automation skills**.
