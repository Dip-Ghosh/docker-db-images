# Multi-Database Docker Setup

### A simple Docker Compose setup for running:

#### MySQL 8
#### PostgreSQL 18
#### Microsoft SQL Server 2022

Perfect for local development, testing, and DataGrip connections.

# 🚀 Features
- MySQL container
-  PostgreSQL container
- SQL Server container
- Persistent Docker volumes
- Auto SQL initialization support
-  Easy DataGrip integration
📁 Project Structure
    dockerDB/
    ├── docker-compose.yml
    ├── mysql-init/
    │   └── init.sql
    ├── postgres-init/
    │   └── init.sql
    └── README.md
### 🐳  Start Containers
    docker compose up -d
### 🛑 Stop Containers
    docker compose down
### ❌ Remove Containers + Volumes
    docker compose down -v
### 🔍 Check Running Containers
### docker ps
### 📦 Database Initialization

Both MySQL and PostgreSQL support automatic SQL execution during first startup. MySQL Initialization

#### Create: mysql-init/init.sql

#### Example:
    CREATE DATABASE school;
    CREATE DATABASE company;
    PostgreSQL Initialization

#### Create: postgres-init/init.sql

#### Example:
    
    CREATE DATABASE analytics;
    CREATE DATABASE hr;
### 🧠 Important Note
Initialization scripts run only during the first container initialization. If databases are not recreated:

    docker compose down -v
    docker compose up -d

### 🔌 DataGrip Connection Setup
#### MySQL
    Field	Value
    Host	localhost
    Port	3306
    User	root
    Password	root123
#### PostgreSQL
    Field	Value
    Host	localhost
    Port	5432
    User	postgres
    Password	postgres123
#### SQL Server
    Field	Value
    Host	localhost
    Port	1433
    User	sa
    Password	StrongPass123!
#### 🛠 Useful Commands
### View Logs
    MySQL : docker logs mysqlserver
    PostgreSQL : docker logs my-postgres
    SQL Server : docker logs sqlserver
### Restart Containers
    docker compose restart
### 📌 Notes
    - PostgreSQL 18 uses the newer /var/lib/postgresql storage layout.
    - SQL Server requires more RAM compared to MySQL/Postgres.
    - Ports must be free before starting containers.