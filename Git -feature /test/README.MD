# **Salary-API POC**

| **Author** | **Created on** | **Version** | **Last updated by**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|---------------------|-------------|-------------|-------------|-------------|
| Anuj Yadac|   12-02-2025             | v1.1          | Anuj Yadav      |  Komal Jaiswal |  |   |      |

# Employee API Setup Guide (PoC)

## **Table of Contents**

<details>
  <summary>System Setup</summary>

  - [1. Update Package List](#1-update-package-list)
  - [2. Git Clone Repository](#2-git-clone-repository)

</details>

<details>
  <summary>Golang Setup</summary>

  - [3. Install Golang](#3-install-golang)
  - [4. Install Make](#4-install-make)
  - [5. Install jq](#5-install-jq)

</details>

<details>
  <summary>ScyllaDB Setup</summary>

  - [6. Install ScyllaDB](#6-install-scylladb)
  - [7. Configure ScyllaDB](#7-configure-scylladb)
  - [8. Connect to ScyllaDB using cqlsh](#8-connect-to-scylladb-using-cqlsh)
  - [9. Create Superuser & Keyspace](#9-create-superuser--keyspace)
  - [10. Update Configuration File](#10-update-configuration-file)

</details>

<details>
  <summary>Redis Setup</summary>

  - [11. Install Redis](#11-install-redis)
  - [12. Configure Redis CLI](#12-configure-redis-cli)
  - [13. Update Redis Configuration](#13-update-redis-configuration)

</details>

<details>
  <summary>Database Migration</summary>

  - [14. Install Migrate Tool](#14-install-migrate-tool)
  - [15. Run Database Migrations](#15-run-database-migrations)

</details>

<details>
  <summary>Application Setup</summary>

  - [16. Test the Application](#16-test-the-application)
  - [17. Configure main.go File](#17-configure-maingo-file)
  - [18. Run the Application](#18-run-the-application)
  - [19. Test via Swagger UI](#19-test-via-swagger-ui)

</details>

<details>
  <summary>Authors</summary>

  - [20. Contributors](#20-contributors)

</details>

## System Setup

### 1. Update Package List
```bash
sudo apt update
```
- Updating the Package List

### 2. Git Clone Repository
```bash
git clone https://github.com/OT-MICROSERVICES/employee-api.git
cd employee-api/
```
- Cloning the Git Repository for Employee API Setup

## Golang Setup

### 3. Install Golang
[Refer to the Golang installation guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Anuj-SCRUM-6/Common/Software/Golang/Installation).
```bash
go version
```
- go version go1.22.2 linux/amd64

### 4. Install Make
```bash
make --version
```
- GNU Make Version: 4.3
- Make automates the build process by executing defined tasks and dependencies.

### 5. Install jq
```bash
sudo apt install jq -y
jq --version
```
- jq version is 1.7.1.
- jq is a command-line tool for processing and manipulating JSON data.

## ScyllaDB Setup

### 6. Install ScyllaDB
[Refer to the ScyllaDB Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Rohit-SCRUM-16/OT%20MS%20Understanding/Database/ScyllaDB/POC).
```bash
scylla --version
```
- Scylla version is 6.2.3.

### 7. Configure ScyllaDB
[Refer to the ScyllaDB Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/0f733ece2fe86ac7ecc0bb83937310b5698e63fa/Common/Software/ScyllaDB/Configuration).

### 8. Connect to ScyllaDB using cqlsh
```bash
cqlsh <Private-IP> 9042 -u cassandra -p cassandra
```
**Example**
```bash
cqlsh 172.31.0.27 9042 -u cassandra -p cassandra
```
- Connects to ScyllaDB using CQLSH.

### 9. Create Superuser & Keyspace
```bash
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
```

### 10. Update Configuration File
```bash
localhost/<Private-IP>:8080/---> config.yaml
```
- Update config.yaml with the correct Private-IP and port.

## Redis Setup

### 11. Install Redis
[Refer to the Redis Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Mohit-SCRUM-12/Common/Software/Redis/Installation/README.md).
```bash
redis-server --version
```
- Redis version is 7.0.15.

### 12. Configure Redis CLI
```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
```

## Database Migration

### 14. Install Migrate Tool
[Refer to the Migration Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Nikita-SCRUM-8/Common/Software/Migration/Installation/README.md).
```bash
migrate --version
```

### 15. Run Database Migrations
```bash
make run-migrations
```

## Application Setup

### 16. Test the Application
```bash
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```

### 17. Configure main.go File
[Refer to the main.go Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Anuj-SCRUM-6/Common/Software/Golang/Configuration/README.md).

### 18. Run the Application
```bash
go run main.go
```

### 19. Test via Swagger UI
```bash
http://<Public-IP>:8080/swagger/index.html
```

## Authors

### 20. Contributors
| Name | Email Address | GitHub | URL |
|------|--------------|--------|-----|
| Anuj Yadav | anuj.yadav@mygurukulam.co | [anuj169](https://github.com/anuj169) | https://github.com/anuj169 |
