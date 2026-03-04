# 🚀 Jenkins CI Pipeline with Maven and Spring Boot

---

## 📌 Project Overview

This project demonstrates a **Continuous Integration (CI) pipeline using Jenkins integrated with GitHub**.

The application used in this pipeline is a simple **Spring Boot Employee API built with Maven**. Jenkins automatically reads the **Jenkinsfile from the GitHub repository** and executes the pipeline to build and package the application.

This project showcases how modern DevOps workflows automate the following processes:

- Pulling source code from GitHub  
- Building the application using Maven  
- Running automated tests  
- Packaging the application as an executable JAR artifact  

It demonstrates a practical **CI pipeline workflow used in real DevOps environments**.

---

## ⚙️ Tech Stack

- Java 17  
- Spring Boot  
- Maven  
- Jenkins  
- Git  
- GitHub  

---

## 📂 Project Structure

```
jenkins-ci
│
├── Jenkinsfile
├── pom.xml
├── README.md
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

The **Jenkinsfile** defines the following pipeline stages:

### 1️⃣ Checkout
Pulls the latest source code from the GitHub repository.

### 2️⃣ Build

```
mvn compile
```

Compiles the project source code.

### 3️⃣ Test

```
mvn test
```

Runs the automated tests.

### 4️⃣ Package

```
mvn package
```

Packages the application and generates the final **JAR artifact**.

---

## 🔄 CI Pipeline Workflow

```
Developer Push Code → GitHub
           ↓
        Jenkins
           ↓
        Checkout
           ↓
         Build
           ↓
          Test
           ↓
        Package
           ↓
     Artifact (.jar)
```

---

## 📦 Generated Artifact

After the pipeline execution, Maven generates the build artifact:

```
target/employee-api-1.0.jar
```

This artifact can later be used for **deployment to servers, containers, or cloud environments**.

---

## ▶️ Run Application Manually (Optional)

Build the project:

```
mvn package
```

Run the application:

```
java -jar target/employee-api-1.0.jar
```

---

## 🌐 Example Endpoint

If the application is executed manually, it can be accessed at:

```
http://localhost:8080/
```

Example response:

```
Welcome to Employee API - Jenkins CI Pipeline Working!
```

---

## 🎯 What This Project Demonstrates

This project proves understanding of:

- Jenkins CI pipeline creation  
- GitHub integration with Jenkins  
- Pipeline as Code using **Jenkinsfile**  
- Maven build lifecycle  
- Automated build, test, and packaging  
- Artifact generation in CI pipelines  

---

## 💼 Why This Project Matters

This repository demonstrates real-world DevOps practices including:

- Continuous Integration (CI)  
- Build automation  
- Source control integration  
- Artifact generation for deployment workflows  

These are core skills required in **modern DevOps and cloud environments**.

---

## 👨‍💻 Author

Developed as part of hands-on practice to strengthen **AWS, DevOps, and CI/CD pipeline skills**.
