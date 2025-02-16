# Employee API POC


| **Author** | **Created on** | **Version** | **Last updated by**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|---------------------|-------------|-------------|-------------|-------------|
| Anuj Yadac|   12-02-2025             | v1.1          | Anuj Yadav      |  Komal Jaiswal |  |   |      |

# Employee API Setup Guide (PoC)

## **Table of Contents**

<details>
  <summary>System Setup</summary>

  - [ Update Package List](#1-update-package-list)
  - [ Git Clone Repository](#2-git-clone-repository)

</details>

<details>
  <summary>Golang Setup</summary>

  - [ Install Golang](#3-install-golang)
  - [ Install Make](#4-install-make)
  - [ Install jq](#5-install-jq)

</details>

<details>
  <summary>ScyllaDB Setup</summary>

  - [ Install ScyllaDB](#6-install-scylladb)
  - [ Configure ScyllaDB](#7-configure-scylladb)
  - [ Connect to ScyllaDB using cqlsh](#8-connect-to-scylladb-using-cqlsh)
  - [ Create Superuser & Keyspace](#9-create-superuser--keyspace)
  - [ Update Configuration File](#10-update-configuration-file)

</details>

<details>
  <summary>Redis Setup</summary>

  - [ Install Redis](#11-install-redis)
  - [ Configure Redis CLI](#12-configure-redis-cli)
  - [ Update Redis Configuration](#13-update-redis-configuration)

</details>

<details>
  <summary>Database Migration</summary>

  - [ Install Migrate Tool](#14-install-migrate-tool)
  - [ Run Database Migrations](#15-run-database-migrations)

</details>

<details>
  <summary>Application Setup</summary>

  - [ Test the Application](#16-test-the-application)
  - [ Configure main.go File](#17-configure-maingo-file)
  - [ Run the Application](#18-run-the-application)
  - [ Test via Swagger UI](#19-test-via-swagger-ui)

</details>

<details>
  <summary>Authors</summary>

  - [ Contributors](#20-contributors)

</details>

## System Setup

###  Update Package List
```bash
sudo apt update
```
- Updating the Package List

###  Git Clone Repository
```bash
git clone https://github.com/OT-MICROSERVICES/employee-api.git
cd employee-api/
```
- Cloning the Git Repository for Employee API Setup

## Golang Setup

###  Install Golang
[Refer to the Golang installation guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Anuj-SCRUM-6/Common/Software/Golang/Installation).
```bash
go version
```
- go version go1.22.2 linux/amd64

###  Install Make
 [Refer to the Make installation guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Nikita-SCRUM-8/Common/Software/Make/Installation%20)
 
```bash
make --version
```
- GNU Make Version: 4.3
- Make automates the build process by executing defined tasks and dependencies.

###  Install jq
```bash
sudo apt install jq -y
jq --version
```
- jq version is 1.7.1.
- jq is a command-line tool for processing and manipulating JSON data.

## ScyllaDB Setup

###  Install ScyllaDB
[Refer to the ScyllaDB Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Rohit-SCRUM-16/OT%20MS%20Understanding/Database/ScyllaDB/POC).
```bash
scylla --version
```
- Scylla version is 6.2.3.

###  Configure ScyllaDB
[Refer to the ScyllaDB Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/0f733ece2fe86ac7ecc0bb83937310b5698e63fa/Common/Software/ScyllaDB/Configuration).

###  Connect to ScyllaDB using cqlsh
```bash
cqlsh <Private-IP> 9042 -u cassandra -p cassandra
```
**Example**
```bash
cqlsh 172.31.0.27 9042 -u cassandra -p cassandra
```
- The command connects to a ScyllaDB instance at <private_IP> on port 9042 using the cqlsh tool, with the username and password set to cassandra.
- Connects to the ScyllaDB server using CQLSH, allowing you to execute queries, manage keyspaces, and interact with the database.


###  Create Superuser & Keyspace
```bash
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
```
Note:
- Never use the default username and password when setting up your database. It is important to use a strong password for security best 
  practices.

- Create a new user in ScyllaDB with limited control over keyspaces, tables, and permissions. This approach is useful when you want to move 
  away from the default cassandra user and use a dedicated admin user for better security.


```bash
CREATE USER scylladb WITH PASSWORD 'strongpassword' NOSUPERUSER;
```

- This command creates a new user scylladb with the specified strong password and without superuser privileges.
- Grant specific permissions to the newly created user for accessing and modifying data in the keyspace.


```bash
GRANT SELECT, MODIFY ON KEYSPACE employee_db TO scylladb;
```
- SELECT: Allows reading data from the keyspace.
- MODIFY: Allows inserting, updating, and deleting records in the keyspace




###  Update Configuration File
```bash
  172.31.0.27 :8080/---> config.yaml
```
- Update config.yaml with Private IP

## Redis Setup

### 11. Install Redis
[Refer to the Redis Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Mohit-SCRUM-12/Common/Software/Redis/Installation/README.md).
```bash
redis-server --version
```
- Redis version is 7.0.15.

###  Configure Redis CLI
```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
```
###  Update Redis Configuration

- [Kindly follow the link below for this](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Mohit-SCRUM-12/Common/Software/Redis/Configuration).
- Opens the Redis configuration file for editing. To bind Redis to specific IP addresses (e.g., 127.0.0.1,172.31.24.234 and a private IP) for security and accessibility.

## Database Migration

###  Install Migrate Tool
[Refer to the Migration Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Nikita-SCRUM-8/Common/Software/Migration/Installation/README.md).
```bash
migrate --version
```
- Migrate version is v4.16.2.
###  Run Database Migrations
```bash
make run-migrations
```

## Application Setup

###  Test the Application
```bash
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```

###  Configure main.go File
[Refer to the main.go Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Anuj-SCRUM-6/Common/Software/Golang/Configuration/README.md).

###  Run the Application
```bash
go run main.go
```

###  Test via Swagger UI
```bash
http://<Public-IP>:8080/swagger/index.html
```

## Authors

###  Contributors
| Name | Email Address | GitHub | URL |
|------|--------------|--------|-----|
| Anuj Yadav | anuj.yadav@mygurukulam.co | [anuj169](https://github.com/anuj169) | https://github.com/anuj169 |
