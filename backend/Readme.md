# Spring Boot Backend Deployment Guide 

## Prerequisites

- Java Development Kit (JDK 17 or higher) installed.
- Maven installed.
- Spring Boot application source code or JAR file.

## Step 1: Install Java

1. Verify if Java is installed by running the following command:

   ```bash
   java -version
   ```

If Java is not installed, install the JDK from OpenJDK.

```shell
apt update && apt install openjdk-17-jdk -y
java -version
```

## Step 2: Install Maven

Installing maven in ubuntu:

```shell
apt install maven -y
```

### Verify Maven installation:

```bash

mvn -version
```

## Step 3: Build the Spring Boot Application

### Update DB credentials in application.properties:

```shell
vim src/main/resources/application.properties

   server.port=8080
   spring.datasource.url=jdbc:mariadb://<DB_HOST>:3306/<DB_NAME>
   spring.datasource.username=<DB_USER>
   spring.datasource.password=<DB_PASS>
```

### Build springboot Application using maven

```shell
mvn clean package
```

## Step 4: Run the Application

Run the generated JAR file by using the following command:

```bash

java -jar target\spring-backend-v1.jar
```

The application will start and be accessible at:

http://localhost:8080

### Step 5: Keep the Application Running

To keep the application running in the background, you can use nohup or a similar method. 

### History 
```bash
git clone https://github.com/mukundDeo9325/student_app1.git
    2  ls
    3  cd student_app1/
    4  ls
    5  cd backend/
    6  ls
    7  apt install mysql-client -y
   10  mysql -h database-1.ch22ygm442ex.ap-south-1.rds.amazonaws.com -u admin -p
   11  ls
   12  java -version
   13  apt update && apt install openjdk-17-jdk -y
   14  java -version
   15  apt install maven -y
   16  ls
   17  cd student_app1/
   18  ls
   19  cd backend/
   20  ls
   21  apt install maven -y
   22  mvn -version
   23  ls
   24  vim src/main/resources/application.properties 
   25  ls
   26  mvn clean package
   27  lz
   28  ls
   29  cd target/
   30  ls
   31  java -jar student-registration-backend-0.0.1-SNAPSHOT.jar
```



