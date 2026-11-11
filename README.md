# Java Application Deployment on Rocky Linux 9.8

A hands-on Linux System Administration project demonstrating the manual deployment of a Java Spring Boot web application on Rocky Linux 9.8.

## Project Overview

This project demonstrates how to deploy a Java Spring Boot application on a Linux server using OpenJDK 21 and Apache Maven.

The application is packaged as an executable JAR, launched using the Java runtime, and made accessible over the network by configuring the Linux firewall.

The deployment was performed on a Rocky Linux 9.8 virtual machine using VMware Workstation, with the application accessed from a Windows host through Google Chrome.

## Technology Stack

| Technology | Purpose |
|---|---|
| Rocky Linux 9.8 | Server operating system |
| OpenJDK 21 | Java runtime and compiler |
| Spring Boot | Application framework |
| Apache Maven | Build and dependency management |
| Apache Tomcat | Embedded application server |
| firewalld | Linux firewall management |
| VMware Workstation | Virtualization |
| Git & GitHub | Version control and project hosting |

## Deployment Architecture

```text
       Windows Host
       Google Chrome
             |
             | HTTP Request
             | TCP Port 8080
             |
             v
    Rocky Linux 9.8 VM
             |
             v
       firewalld
      Allow TCP 8080
             |
             v
    Embedded Apache Tomcat
             |
             v
     Spring Boot Application
             |
             v
       HTTP Response
```

## Project Structure

```text
java-app-deployment-rhel9/
│
├── .gitignore
├── README.md
│
├── screenshots/
│   ├── chrome.png
│   └── putty.png
│
└── java-deployment-app/
    ├── pom.xml
    ├── mvnw
    ├── mvnw.cmd
    │
    └── src/
        ├── main/
        │   ├── java/
        │   │   └── com/example/java
