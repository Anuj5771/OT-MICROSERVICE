# Employee Poc Setup
  
| **Author**    | **Created on** | **Version** | **Last updated by** | **Internal Reviewer** | **Reviewer L0** | **Reviewer L1** | **Reviewer L2** |
|---------------|----------------|-------------|---------------------|-----------------------|-----------------|-----------------|-----------------|
| Anuj Yadav    | 12-02-2025     | v1.1        | Anuj Yadav          | Komal Jaiswal         |                 |                 |                 |

# Step-by-step Installation of Employee API

## Employee API Setup Guide  

### Table of Contents  
1. [System Setup](#system-setup)  
   - [Update Package List](#update-package-list)  
   - [Git Clone Repository](#git-clone-repository)  
2. [Golang Setup](#golang-setup)  
   - [Install Golang](#install-golang)  
   - [Install Make](#install-make)  
   - [Install jq](#install-jq)  
3. [ScyllaDB Setup](#scylladb-setup)  
   - [Install ScyllaDB](#install-scylladb)  
   - [Configure ScyllaDB](#configure-scylladb)  
   - [Connect to ScyllaDB using cqlsh](#connect-to-scylladb-using-cqlsh)  
   - [Create Superuser & Keyspace](#create-superuser--keyspace)  
   - [Update Configuration File](#update-configuration-file)  
4. [Redis Setup](#redis-setup)  
   - [Install Redis](#install-redis)  
   - [Configure Redis CLI](#configure-redis-cli)  
   - [Update Redis Configuration](#update-redis-configuration)  
5. [Database Migration](#database-migration)  
   - [Install Migrate Tool](#install-migrate-tool)  
   - [Run Database Migrations](#run-database-migrations)  
6. [Application Setup](#application-setup)  
   - [Test the Application](#test-the-application)  
   - [Configure main.go File](#configure-maingo-file)  
   - [Run the Application](#run-the-application)  
   - [Test via Swagger UI](#test-via-swagger-ui)  
7. [Authors](#authors)

---

### 1. Update Package List
```bash
sudo apt update
```
  Updates the list of available packages and their versions from the configured repositories.
 Ensures you have the latest information about available software packages before installing anything.

---

### 2. Git clone repository 
```bash
 git clone https://github.com/OT-MICROSERVICES/employee-api.git
 cd employee-api/
```

Clones the `Employee API` repository from GitHub to your local machine.

To get the source code of the project so you can set it up and run it locally

---


### 3.  Golang Installation 

- To install Golang on your system, please follow the link below for the Go Installation Guide.

[Golang Installation](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Anuj-SCRUM-6/Common/Software%20/Golang/Installation)

```bash
go version
```
- go version go1.22.2 linux/amd64

### 4.  Install make

- The command sudo apt install make installs the make utility on a Debian-based system like Ubuntu, which is used for building and managing 
  projects from Makefiles.

```bash
  sudo apt install make
  make --version
```
- GNU Make Version: 4.3


### 5.  Install jq 
- This command installs the jq package on an Ubuntu/Debian system without asking for confirmation.
```bash
 sudo apt install -y jq
 jq --version
```
- jq version is 1.7.1.


### 6. Install scyllaDB

- To install ScyllaDB on your system, please follow the link below for the ScyllaDB Installation Guide.

[Installatioon ScyllaDB](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Rohit-SCRUM-16/OT%20MS%20Understanding/Database/ScyllaDB/POC)

```bash
scylla --version
```
- Scylla version is 6.2.3.

### 7. To configure scyllaDB
- Follow the link below to configure ScyllaDB

 [Configure ScyllaDB ](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/0f733ece2fe86ac7ecc0bb83937310b5698e63fa/Common/Software/ScyllaDB/Configuration)

In ScyllaDB rpc_address defines the IP address that Scylla listens on for client connections, enabling communication between nodes via RPC in a distributed system.

### 8. Connect to scyllaDB/Cassandra database using cqlsh

```bash
 cqlsh 172.31.44.148 -u cassandra -p cassandra

```
This command connects to the ScyllaDB/Cassandra database using cqlsh with the specified IP, username, and password.


### 9. Creating a superuser and Keyspace in cassandra

```bash
 CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
 CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };

```
This creates a superuser named scylladb and a keyspace employee_db with a replication factor


### 10.  Configuration file config.yml

```bash
  config.yml ---> Private-ip
```
- Replace "localhost//8080" with private IP in config.yml


### 11. Redis Installation  

- To install Redis on your system, please follow the link below for the Redis Installation Guide.

[ Redis Installation ](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Mohit-SCRUM-12/Common/Software/Redis/Installation/README.md)

```bash
redis-server --version
```
- Redis version is 7.0.15.

### 12. Redis cli configure
```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
```

### 13. Update the redis configuration 

- To update the Redis configuration, follow the link below 

[Update the Redis configuration ](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Mohit-SCRUM-12/Common/Software/Redis/Configuration)

 Opens the Redis configuration file for editing.
 To bind Redis to specific IP addresses (e.g., `127.0.0.1,172.31.24.234` and a private IP) for security and accessibility.

---

### 14. Install migrate tool
```bash
  curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
  sudo mv migrate /usr/local/bin/migrate
  migrate --version

```
Downloads, extracts, moves the migrate tool to the system path, and checks its version.

### 15. Running Database Migrations with Changes Private IP
```bash
  migration.json ----> Private-ip

  make run-migrations

```


### 16. Test the application
```bash
 go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```
Runs tests for the Go application, excluding specific directories and files, and generates a test coverage report.


### 17. Configuration the main.go files
- Refer to the main.go Configuration Guide for setup details.

[Configuration the main.go files](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Anuj-SCRUM-6/Common/Software%20/Golang/Configuration/README.md)


### 18. Run the application
```bash
go run main.go
```

### 19. Test the application via swagger UI
```bash

 http://public ip:8080/swagger/index.html
```


## Authors


| Name| Email Address      | GitHub | URL |
|-----|--------------------------|----------|---------|
|Anuj yadav |anuj.yadav@mygurukulam.co |  [anuj169](anuj169)  | https://github.com/anuj169
