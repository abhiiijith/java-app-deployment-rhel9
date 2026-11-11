# Java Application Deployment on Rocky Linux 9.8

A hands-on Linux administration project demonstrating the manual deployment of a Java Spring Boot web application on Rocky Linux 9.8.

## Project Overview

This project covers the complete process of preparing a Linux server, building a Spring Boot application, deploying an executable JAR, configuring the Linux firewall, and accessing the application from a remote web browser.

## Technology Stack

- **Operating System:** Rocky Linux 9.8
- **Programming Language:** Java 21
- **Framework:** Spring Boot
- **Build Tool:** Apache Maven
- **Web Server:** Embedded Apache Tomcat
- **Firewall:** firewalld
- **Virtualization:** VMware Workstation
- **Version Control:** Git and GitHub

## Architecture

```text
Windows Host (Chrome)
        |
        | HTTP :8080
        v
Rocky Linux 9.8 VM
        |
        v
firewalld (TCP 8080)
        |
        v
Apache Tomcat
        |
        v
Spring Boot Application
        |
        v
HTTP Response
```

## Implementation

1. Prepared a Rocky Linux 9.8 virtual machine using VMware.
2. Installed and configured OpenJDK 21.
3. Installed Apache Maven.
4. Generated a Spring Boot application using Spring Initializr.
5. Created a REST endpoint using `@RestController` and `@GetMapping`.
6. Packaged the application into an executable JAR.
7. Started the application using `java -jar`.
8. Configured firewalld to allow TCP port 8080.
9. Tested the application using curl.
10. Accessed the deployed application through Chrome on the Windows host.

## Build the Application

```bash
mvn clean package
```

## Run the Application

```bash
java -jar target/java-deployment-app-0.0.1-SNAPSHOT.jar
```

## Firewall Configuration

```bash
firewall-cmd --permanent --add-port=8080/tcp
firewall-cmd --reload
firewall-cmd --list-ports
```

## Verify Deployment

Test locally:

```bash
curl http://localhost:8080/
```

Access from another machine on the same network:

```text
http://<VM-IP-ADDRESS>:8080/
```

Expected response:

```text
Hello! Java application deployed successfully on Linux!
```

## Skills Demonstrated

- Linux server administration
- Java runtime installation and configuration
- Maven application builds
- Spring Boot application deployment
- JAR packaging and execution
- Firewall configuration and port management
- HTTP troubleshooting and application verification
- Git version control and GitHub publishing

## Future Improvements

- Configure Nginx as a reverse proxy.
- Manage the application using systemd.
- Implement automated deployment.
- Introduce Docker containerization and CI/CD.

---

**Project Status:** Manual deployment completed successfully.
