# React Project Setup and Deployment Guide for Windows

This guide provides step-by-step instructions for setting up a React project.

## 1. Setting Up the React Project

### Install Node.js and npm

```shell
apt update && apt install nodejs npm -y
```

### Verify Installation


```shell
node -v
npm -v
```


## 2. Install Dependencies

To install the necessary dependencies for your project, run the following command:

```shell
npm install
```

## 3. Build the React Application for Production

Update backend URL in .env file

```shell
vim .env 

    VITE_API_URL = "http://<BACKEND_PUBLIC_IP>:8080/api"
```

To build the React application for production, run:

```shell
npm run build
```

This will create a dist/ directory in your project containing optimized, production-ready files.

## 4. Deploy production-ready files on s3 or apache2 server

```shell
apt install apache2 -y
systemctl start apache2
cp -rf dist/* /var/www/html/
```

You can access the application on http://localhost:80
### History 
```bash
1  git clone https://github.com/mukundDeo9325/student_app1.git
    2  ls
    3  cd student_app1/
    4  ls
    5  cd frontend/
    6  ls
    7  ls -a
    8  vim .env 
    9  apt update && apt install nodejs npm -y
   10  npm install
   11  npm run build
   12  apt install apache2 -y
   13  systemctl start apache2
   14  cp -rf dist/* /var/www/html/
   15  apt install mysql-client -y 
   16  mysql -h database-1.ch22ygm442ex.ap-south-1.rds.amazonaws.com -u admin -predhat123
   17  history
```

