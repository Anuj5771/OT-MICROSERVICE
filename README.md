| **Author** | **Created on** | **Version** | **Last updated by**|**Internal Reviewer** |**Reviewer L0** |**Reviewer L1** |**Reviewer L2** |
|------------|---------------------------|-------------|---------------------|-------------|-------------|-------------|-------------|
| Anuj yadav|   12-02-2025             | v1.1          | Anuj yadav        |  Komal Jaiswal |  |   |      |


## Table of Contents

1.  [Introduction](#introduction)
2.  [Why Use PostgreSQL?](#why-use-postgresql)
3.  [Installation Requirements](#installation-requirements)
4.  [PostgreSQL Architecture](#postgresql-architecture)
5.  [Key Concepts](#key-concepts)
6.  [Features](#features)
7.  [Creating and Managing a PostgreSQL Database](#creating-and-managing-a-postgresql-database)
8.  [Advanced Features](#advanced-features)
9.  [Backup & Recovery in PostgreSQL](#backup--recovery-in-postgresql)
10. [High Availability](#high-availability)
11. [Conclusion](#conclusion)
12. [Contact Information](#contact-information)
13. [References](#references)

## What is PostgreSQL?
PostgreSQL is an open-source, object-relational database system that uses SQL. It’s known for its reliability, performance, and support for advanced features like complex queries, custom data types, and ACID compliance.

## Why use PostgreSQL
| Benefits   | Description                     |
| :-------- | :--------------------------------- |
| `Reliable` | Suitable for mission-critical applications. |
| `Scalable`| Handles large datasets and heavy workloads.
| `Open-source`   | Free and has a large community. |
| `Versatile`| Can be used for various applications.   |
| `Feature-rich` |Offers advanced data types, full-text search, and more.

## PostgreSQL Installation Requirements


| **Requirement**          | **Details**                        |
|--------------------------|------------------------------------|
| **OS**                   | Ubuntu 22.04 or 24.04              |
| **RAM**                  | 4 GB minimum                       |
| **Disk Space**           | 10 GB or more                     |
| **Processor**            | Intel Xeon or equivalent           |
| **Instance Type**        | t2.medium (or equivalent)          |
| **Network**              | Port 5432 open for PostgreSQL      |
| **SSH**                  | Port 22 for remote access         |

## Step:1 Update package list
```bash
sudo apt update
```
## Step:2 Install PostgreSQL
```bash
sudo apt install postgresql postgresql-contrib

```
## Verify Installation
```bash
psql --version

```
## Step 4: Start and Enable PostgreSQL Service
```bash
sudo systemctl start postgresql
sudo systemctl enable postgresql

```
 
## Step 5: Access PostgreSQL
```bash
sudo -i -u postgres

```

## Step 6: Exit PostgreSQL Prompt
```bash
\q


```
## Step 7: (Optional) Create a new PostgreSQL role/user
```bash
createuser --interactive --pwprompt

```


## PostgreSQL Architecture


![image](https://github.com/user-attachments/assets/f6e6f42b-a618-4d45-bc95-1132bd4c8f86)

## Features of PostgreSQL
| Feature   | Description                        |
| :-------- | :--------------------------------- |
| `Open Source` | Free and open-source, with a large community and active development.      |
| `High Availability`| Supports replication and clustering for redundancy and fault tolerance.
| `Scalability`   |  Can handle large datasets and heavy workloads. |
| `SQL and NoSQL support`|  Supports both relational (SQL) and some NoSQL features, like JSON and key-value pairs.      |
| `Cross-platform` |Works on various operating systems, including Linux, macOS, and Windows.|

## Key Concepts
| Term   | Description                     |
| :-------- | :--------------------------------- |
| `Database` | A collection of related data objects like tables, views, and functions. |
| `Schema`| A logical grouping of database objects within a database.
| `Table`   |  A structured collection of data records with rows and columns. |
| `Column`| A named attribute of a table that holds specific data types like integers, text, or timestamps       |
| `Row` |A single instance of data in a table, containing values for each column.|
| `SQL (Structured Query Language)` | A standardized language for querying and manipulating data in relational databases.|
| `Indexes` | Data structures that improve query performance by speeding up data retrieval.|
 `Constraints` |Rules that enforce data integrity by restricting the type or format of data allowed in a table.|


## Creating and Managing a PostgreSQL Database
| Rule   | Description                     |
| :-------- | :--------------------------------- |
| `Installation	` |Install PostgreSQL on your system using the package manager or installation files appropriate for your operating system. |
| `Database Creation`| Use the CREATE DATABASE command to create a new database instance for your application.
| `Schema Definition`   |Plan and define the database schema by creating tables, specifying columns, setting data types, and establishing relationships between tables.|
| `Data Manipulation`|Use SQL commands like INSERT, UPDATE, and DELETE to add, modify, or remove data in your tables.   |
| `User Management` |Create database users and manage their permissions by assigning appropriate roles and access rights to ensure data security.

## Advanced Features
| Features   | Description                     |
| :-------- | :--------------------------------- |
| `Advanced Data Types` |JSON, XML, arrays, ranges, and more. |
| `Procedural Languages`| PL/pgSQL for creating custom functions and procedures.
| `Replication`   |For high availability and data redundancy. |
| `Full-Text Search`| For efficient searching of text data.   |
| `Triggers` |For automated actions based on specific events.


## Backup & Recovery in PostgreSQL

    
| **Backup Type**                        | **Description**                                                                 |
|----------------------------------------|---------------------------------------------------------------------------------|
| **SQL Dump (Logical Backup)**          | Exports the database schema and data as SQL statements (e.g., `CREATE TABLE`, `INSERT INTO`). Useful for data transfer and partial restores. |
| **File System Level Backup (Physical Backup)** | Copies the actual database files, logs, and configurations. Efficient for large databases and provides a full, faster restore. Ideal for system recovery. |



## Best Practices & Common Issues

| **Category**        | **Details**                                                                                                 |
|---------------------|-------------------------------------------------------------------------------------------------------------|
| **Best Practices**   | - **Keep software updated** to avoid security risks.<br>- **Use trusted sources** for extensions/plugins.<br>- **Check compatibility** to prevent conflicts. |
| **Common Issues**    | - **Conflicts** between extensions can cause instability.<br>- **Performance issues** from unoptimized plugins.<br>- **Security risks** from outdated plugins. |


---

## Real-World Use Cases

| **Domain**               | **Use Cases**                                                                                                          |
|--------------------------|------------------------------------------------------------------------------------------------------------------------|
| **E-commerce Platforms** | - Payment gateway plugins.<br>- Inventory management integrations.                                                    |
| **Web Browsers**         | - Ad-blocking extensions.<br>- Productivity tools like password managers.                                              |
| **CMS (Content Management Systems)** | - SEO plugins.<br>- Social media integrations.                                                                 |

---

## High Availability

| **Strategy**              | **Details**                                                                                                                |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **Use Load Balancing**    | Distribute traffic across multiple servers to avoid downtime.                                                              |
| **Monitor and Alert**     | Regularly check for issues and set up alerts for potential failures.                                                       |
| **Redundancy**            | Keep backup servers and services to ensure seamless service even during failures.                                           |

---

## Conclusion

|                                                                                                   |
|-------------------------------------------------------------------------------------------------------------------|
| Extensions and plugins enhance application functionality but must be managed carefully to avoid performance issues, security risks, and conflicts. Following best practices and ensuring high availability are crucial for successful implementation. |

## Contacts

| **Name**      | **Email Address**               |
|---------------|----------------------------------|
| Anuj Yadav    | anuj.yadav@mygurukulam.co        |

## Github

| **Username** | **URL**                        |
|--------------|---------------------------------|
| anuj169      | [https://github.com/Anuj5771/](https://github.com/Anuj5771/) |


## Resources

| **Resource**                     | **Description**                             | **Link**                                                        |
|-----------------------------------|---------------------------------------------|-----------------------------------------------------------------|
| PostgreSQL Official Documentation | Official documentation for PostgreSQL       | [PostgreSQL Docs](https://www.postgresql.org/docs/)              |
| PostgreSQL Wiki                   | Community-driven PostgreSQL Wiki            | [PostgreSQL Wiki](https://wiki.postgresql.org/)                  |
| PostgreSQL GitHub Repository      | The official PostgreSQL GitHub repository   | [PostgreSQL GitHub](https://github.com/postgres/postgres)        |
