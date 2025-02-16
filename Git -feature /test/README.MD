# Employee API Setup Guide

## Table of Contents

### 1. System Setup
- [1.1 Update Package List](#11-update-package-list)
- [1.2 Git Clone Repository](#12-git-clone-repository)

### 2. Golang Setup
- [2.1 Install Golang](#21-install-golang)
- [2.2 Install Make](#22-install-make)
- [2.3 Install jq](#23-install-jq)

### 3. ScyllaDB Setup
- [3.1 Install ScyllaDB](#31-install-scylladb)
- [3.2 Configure ScyllaDB](#32-configure-scylladb)
- [3.3 Connect to ScyllaDB using cqlsh](#33-connect-to-scylladb-using-cqlsh)
- [3.4 Create Superuser & Keyspace](#34-create-superuser--keyspace)
- [3.5 Update Configuration File](#35-update-configuration-file)

### 4. Redis Setup
- [4.1 Install Redis](#41-install-redis)
- [4.2 Configure Redis CLI](#42-configure-redis-cli)
- [4.3 Update Redis Configuration](#43-update-redis-configuration)

### 5. Database Migration
- [5.1 Install Migrate Tool](#51-install-migrate-tool)
- [5.2 Run Database Migrations](#52-run-database-migrations)

### 6. Application Setup
- [6.1 Test the Application](#61-test-the-application)
- [6.2 Configure main.go File](#62-configure-maingo-file)
- [6.3 Run the Application](#63-run-the-application)
- [6.4 Test via Swagger UI](#64-test-via-swagger-ui)

### 7. Authors
- [7.1 Contributors](#71-contributors)

---

## 1. System Setup

### 1.1 Update Package List
```bash
sudo apt update
```

### 1.2 Git Clone Repository
```bash
git clone https://github.com/OT-MICROSERVICES/employee-api.git
cd employee-api/
```

---

## 2. Golang Setup

### 2.1 Install Golang
Refer to the [Golang Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Anuj-SCRUM-6/Common/Software%20/Golang/Installation).
```bash
go version
```
 - go version go1.22.2 linux/amd64

### 2.2 Install Make
```bash
sudo apt install make
make --version
```
- GNU Make Version: 4.3

### 2.3 Install jq
```bash
sudo apt install -y jq
jq --version
```
- jq version is 1.7.1.
---

## 3. ScyllaDB Setup

### 3.1 Install ScyllaDB
Refer to the [ScyllaDB Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Rohit-SCRUM-16/OT%20MS%20Understanding/Database/ScyllaDB/POC).
```bash
scylla --version
```
- Scylla version is 6.2.3.

### 3.2 Configure ScyllaDB
Refer to the [ScyllaDB Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/0f733ece2fe86ac7ecc0bb83937310b5698e63fa/Common/Software/ScyllaDB/Configuration).

### 3.3 Connect to ScyllaDB using cqlsh
```bash
cqlsh 172.31.44.148 -u cassandra -p cassandra
```

### 3.4 Create Superuser & Keyspace
```bash
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };
```

### 3.5 Update Configuration File
Update `config.yml` by replacing `localhost//8080` with the private IP.

---

## 4. Redis Setup

### 4.1 Install Redis
Refer to the [Redis Installation Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Mohit-SCRUM-12/Common/Software/Redis/Installation/README.md).
```bash
redis-server --version
```
- Redis version is 7.0.15.

### 4.2 Configure Redis CLI
```bash
redis-cli
ACL SETUSER scylla on >password ~* +@all
```

### 4.3 Update Redis Configuration
Refer to the [Redis Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/tree/Mohit-SCRUM-12/Common/Software/Redis/Configuration).

---

## 5. Database Migration

### 5.1 Install Migrate Tool
```bash
curl -L https://github.com/golang-migrate/migrate/releases/download/v4.15.2/migrate.linux-amd64.tar.gz | tar xvz
sudo mv migrate /usr/local/bin/migrate
migrate --version
```

### 5.2 Run Database Migrations
```bash
make run-migrations
```

---

## 6. Application Setup

### 6.1 Test the Application
```bash
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out
```

### 6.2 Configure main.go File
Refer to the [main.go Configuration Guide](https://github.com/snaatak-Zero-Downtime-Crew/Documentation/blob/Anuj-SCRUM-6/Common/Software%20/Golang/Configuration/README.md).

### 6.3 Run the Application
```bash
go run main.go
```

### 6.4 Test via Swagger UI
```bash
http://public-ip:8080/swagger/index.html
```

---

## 7. Authors

### 7.1 Contributors
| Name | Email Address | GitHub | URL |
|------|--------------|--------|-----|
| Anuj Yadav | anuj.yadav@mygurukulam.co | [anuj169](https://github.com/anuj169) | https://github.com/anuj169 |
