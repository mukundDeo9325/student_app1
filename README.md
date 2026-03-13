# MariaDB Setup and Configuration Guide for Windows

This guide explains how to set up MariaDB, create a database, and Create Database User

## 1. Installing MariaDB

Installing MariaDB on Ubntu

```shell
apt update && apt install mariadb-server -y
```

## 2. Securing MariaDB

Open the Command Prompt as Administrator and run the following command to secure your installation:

```shell

mysql_secure_installation
```

Follow the prompts to:
Set a root password.
Remove insecure default users and test databases.
Disable remote root login.

## 3. Setting Up the Database

Open terminal and login to MariaDB:

```bash

mysql -u root -p
```

Enter the root password when prompted.

---
## for linux use mysql client installation 
```
apt install mysql-client -y
```
```
mysql -h <database_endpoint> -uadmin -p
```
Create a new database and user:

```sql
CREATE DATABASE student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'username'@'localhost' IDENTIFIED BY 'your_password';
```
Replace username and your_password with your desired username and password.
```sql
CREATE DATABASE student_db;
GRANT ALL PRIVILEGES ON springbackend.* TO 'admin'@'localhost' IDENTIFIED BY 'redhat123';
```
Exit MariaDB:

```sql

EXIT;
```


## 4. You will need Database Credentials to Connect Backend with Database
1. DB_HOST
2. DB_USER
3. DB_PASS
4. DB_PORT

5. DB_NAME

```sh
USE student_db;
```
```sh
CREATE TABLE `students` (
  `id` bigint(20) NOT NULL AUTO_INCREMENT,
  `name` varchar(255) DEFAULT NULL,
  `email` varchar(255) DEFAULT NULL,
  `course` varchar(255) DEFAULT NULL,
  `student_class` varchar(255) DEFAULT NULL,
  `percentage` double DEFAULT NULL,
  `branch` varchar(255) DEFAULT NULL,
  `mobile_number` varchar(255) DEFAULT NULL,
  PRIMARY KEY (`id`)
) ENGINE=InnoDB AUTO_INCREMENT=80 DEFAULT CHARSET=latin1 COLLATE=latin1_swedish_ci;
```

---

```
apt install mysql-client -y
    7  mysql -h database-1.c9ky0skqgn78.ap-south-1.rds.amazonaws.com -uadmin -p
    8  ls
    9  cd backend/
   10  ls
   11  nano src/main/resources/application.properties 
   12  ls
   13  docker build . -t backend:v1
   14  docker run -d -p 8080:8080 --name backend backend:v1
   15  docker ps
   16  cd ../frontend/
   17  nano .env
   18  docker build . -t frontend:v1
   19  docker run -d -p 80:80 --name frontend frontend:v1 
   20  docker ps
   21  history
   22  mysql -h database-1.c9ky0skqgn78.ap-south-1.rds.amazonaws.com -uadmin -p
   23  cd
   24  ls
   25  history 

```








