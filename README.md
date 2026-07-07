# Student Registration Form(Dynamic Website-LEMP Stack)
### Introduction

The Student Registration Form is a dynamic web application developed and deployed on an Amazon EC2 (Amazon Linux) instance using the LEMP Stack (Linux, NGINX, MySQL, PHP). The application allows users to submit their registration details through a web form, with the data securely stored in a MySQL database. This project provided hands-on experience in integrating the frontend, backend, and database while deploying a dynamic web application on AWS.
### Architechture Overview
![](./img/Architecture%20diagram.png)
* Amazon Linux (EC2)
* NGINX Web Server
* PHP->Backend
* MySQL Database
* HTML, CSS
* Linux Commands
* Bash Shell Scripting
### Features
* User registration form
* Data stored in database
* Dynamic data handling using PHP
* Server-side processing
* Accessible through server IP
## Steps I  Followed
1. Launch Amazon Linux Instance
* Created EC2 instance
![](./img/1.png)
*  Connected using SSH
![](./img/2.png)

2. Changed the system hostname

sudo hostnamectl hostname registration-form
![](./img/3.png)

3. Created a Bash shell script (lemp.sh) using the Vim editor

![](./img/4.png)

Opened the LEMP.sh file in the Vim editor and added the Bash commands to install, configure, and start the LEMP stack services.<br>

sudo yum update -y<br>
sudo yum install nginx mariadb105-server php -y <br>
sudo systemctl start nginx mariadb php-fpm<br>
sudo systemctl enable nginx mariadb php-fpm<br>

cd /usr/share/nginx/html/<br>
echo "Hello from LEMP.sh file" > index.html
![](./img/5.png)

4. Execute the Bash Shell Script<br>

sudo bash LEMP.sh
![](./img/6.png)

5. Verify the Status of LEMP Services

sudo systemctl status nginx mariadb php-fpm
![](./img/7.png)

6. Create Project Files

* signup.html->for UI
* submit.php->for backend
![](./img/8.png)

7. Setup Database

* Login To MySQL:<br>
mysql -u root -p

* Create database:<br>
CREATE DATABASE FCT;

* Create table:<br>
USE FCT;

CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,<br>
    name VARCHAR(20),<br>
    email VARCHAR(100),<br>
    website VARCHAR(255),<br>
    gender VARCHAR(6),<br>
    comment VARCHAR(100)<br>
);
![](./img/9.png)

8. Download connector

sudo yum install php8.5-mysqlnd.x86_64 -y
![](./img/10.png)

9. Access Website

* open browser<br>
* Enter EC@ public IP
* Fill The Form->Data stored in database
![](./img/11.png)
#
![](./img/12.jpeg)

### What I Learned
* Deploying a dynamic web application on an AWS EC2 instance.
* Installing and configuring the LEMP Stack (Linux, NGINX, MySQL, PHP).
* Connecting a PHP application with a MySQL database.
* Managing Linux services using systemctl.
* Automating server setup using Bash shell scripting.
* Verifying application deployment and service status in a Linux environment.

### summary
This project provided hands-on experience in deploying a dynamic web application using the LEMP Stack on AWS. It enhanced my understanding of web server configuration, database integration, Bash shell scripting, and Linux server management while strengthening my practical DevOps and cloud deployment skills.

