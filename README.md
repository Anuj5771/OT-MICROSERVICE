| Created/Modified | Version | Author               | Comment         | L0 Reviewer      |L1 Reviewer | L2 Reviewer |
|-------------------|---------|----------------------|-----------------|------------------|------------------|------------------|
| 10-02-2024        | V1     | Anuj yadav | L0    |  komal Jaiswal |    |    |

## What is PostgreSQL?
PostgreSQL is an open-source, object-relational database system that uses SQL. It’s known for its reliability, performance, and support for advanced features like complex queries, custom data types, and ACID compliance.

## Table of Contents
1. [Introduction](#introduction)
2. [Features](#features)
3. [Key Concepts](#key-concepts)
4. [Why Use PostgreSQL?](#why-use-postgresql)
5. [Creating and Managing a PostgreSQL Database](#creating-and-managing-a-postgresql-database)
6. [Common SQL Commands](#common-sql-commands)
7. [Advanced Features](#advanced-features)
8. [Conclusion](#conclusion)
9. [Contact Information](#contact-information)
10. [References](#references)


## Why use PostgreSQL
| Benefits   | Description                     |
| :-------- | :--------------------------------- |
| `Reliable` | Suitable for mission-critical applications. |
| `Scalable`| Handles large datasets and heavy workloads.
| `Open-source`   | Free and has a large community. |
| `Versatile`| Can be used for various applications.   |
| `Feature-rich` |Offers advanced data types, full-text search, and more.

# PostgreSQL Installation Requirements


| **Requirement**          | **Details**                        |
|--------------------------|------------------------------------|
| **OS**                   | Ubuntu 22.04 or 24.04              |
| **RAM**                  | 4 GB minimum                       |
| **Disk Space**           | 10 GB or more                     |
| **Processor**            | Intel Xeon or equivalent           |
| **Instance Type**        | t2.medium (or equivalent)          |
| **Network**              | Port 5432 open for PostgreSQL      |
| **SSH**                  | Port 22 for remote access         |


# PostgreSQL Dependencies on Ubuntu

| **Category**                   | **Package(s)**                                                                 |
|---------------------------------|-------------------------------------------------------------------------------|
| **Core PostgreSQL Packages**    | `postgresql`, `postgresql-contrib`                                             |
| **Development Libraries**       | `postgresql-server-dev-all`, `build-essential`, `libssl-dev`, `libreadline-dev`, `zlib1g-dev`, `libicu-dev`, `libxml2-dev` |
| **Optional Libraries**          | `libbz2-dev`, `python3`                                                       |
| **PostgreSQL Extensions**       | `postgis` (for GIS), `pg_partman` (for partitioning)                          |
| **GUI Tools**                   | `pgadmin4` (for GUI management of PostgreSQL)                                  |
| **Compression Tools**           | `bzip2`, `xz-utils`, `lz4`                                                    |


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

 ### Types of Backup Methods in PostgreSQL:
    
| Backup Type                         | Description                                                                 |
| :----------------------------------- | :--------------------------------------------------------------------------- |
| **SQL Dump (Logical Backup)**        | A logical backup refers to exporting the database's data and schema into a human-readable format, such as SQL statements. It contains `CREATE TABLE`, `INSERT INTO`, and other SQL queries, which can be used to recreate the database structure and data. This backup is useful for transferring data between different systems or for selectively restoring parts of the database. |
| **File System Level Backup (Physical Backup)** | A physical backup involves copying the actual data files (e.g., database files, logs, and configuration files) directly from the file system. This type of backup captures the entire database in its current state and is more efficient for large databases, as it includes everything needed to restore the database exactly as it was. It's ideal for full system recovery and can be faster to restore compared to logical backups. |


# Extensions & Plugins

| **Section**                   | **Details**                                                                                                                                 |
|-------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------|
| **What are Extensions & Plugins?** | Add-ons that increase the functionality of an application. Typically integrate third-party services.                                         |
| **Common Use Cases**           | - Enhancing website functionality.<br>- Integrating with external APIs and services.                                                      |

---

# Best Practices & Common Issues

| **Category**            | **Details**                                                                                                                |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **Best Practices**       | - **Keep software updated**: Ensure that all extensions and plugins are up-to-date to avoid security vulnerabilities.<br>- **Choose reliable sources**: Only use extensions and plugins from trusted developers or marketplaces to avoid introducing malware.<br>- **Test for compatibility**: Regularly check that extensions do not conflict with each other or your core system. |
| **Common Issues**        | - **Conflicts between extensions**: Two or more extensions/plugins can conflict, causing instability.<br>- **Performance problems**: Certain plugins might slow down your system if not optimized.<br>- **Security risks**: Unmaintained plugins can introduce vulnerabilities. |

---

# Real-World Use Cases

| **Domain**               | **Use Cases**                                                                                                          |
|--------------------------|------------------------------------------------------------------------------------------------------------------------|
| **E-commerce Platforms** | - Payment gateway plugins.<br>- Inventory management integrations.                                                    |
| **Web Browsers**         | - Ad-blocking extensions.<br>- Productivity tools like password managers.                                              |
| **CMS (Content Management Systems)** | - SEO plugins.<br>- Social media integrations.                                                                 |

---

# High Availability

| **Strategy**              | **Details**                                                                                                                |
|---------------------------|----------------------------------------------------------------------------------------------------------------------------|
| **Use Load Balancing**    | Distribute traffic across multiple servers to avoid downtime.                                                              |
| **Monitor and Alert**     | Regularly check for issues and set up alerts for potential failures.                                                       |
| **Redundancy**            | Keep backup servers and services to ensure seamless service even during failures.                                           |

---

# Conclusion

| **Summary**                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------|
| Extensions and plugins are essential for extending the functionality of applications. However, they must be managed properly to avoid performance issues, security risks, or conflicts. Following best practices and ensuring high availability are key to successful implementation.                                                                 |


## Contacts

| **Name**      | **Email Address**               |
|---------------|----------------------------------|
| Anuj Yadav    | anuj.yadav@mygurukulam.co        |

## Github

| **Username** | **URL**                        |
|--------------|---------------------------------|
| anuj169      | [https://github.com/Anuj5771/](https://github.com/Anuj5771/) |


## Resources

| **Resource**                      | **Description**                               | **Link**                                |
|------------------------------------|-----------------------------------------------|-----------------------------------------|
| PostgreSQL Official Documentation  | Official documentation for PostgreSQL         | [PostgreSQL Docs](https://www.postgresql.org/docs/) |
| PostgreSQL Wiki                    | Community-driven PostgreSQL Wiki              | [PostgreSQL Wiki](https://wiki.postgresql.org/) |
| PostgreSQL GitHub Repository       | The official PostgreSQL GitHub repository     | [PostgreSQL GitHub](https://github.com/postgres/postgres) |


