# MySQL Server
```
// Install MySQL Server
curl -sSLO https://dev.mysql.com/get/mysql80-community-release-el7-5.noarch.rpm
sudo rpm -ivh mysql57-community-release-el7-9.noarch.rpm
sudo yum install mysql-server
systemctl start mysqld
systemctl enable mysqld

// Install MariaDB Server
sudo yum install mariadb-server
sudo vi /etc/my.cnf #configure the file with the right port
systemctl start mariadb
systemctl enable mariadb

// Initialize
mysql -u root -pP@ssw0rd123
> SET PASSWORD = PASSWORD('P@ssw0rd123');
> FLUSH PRIVILEGES;

// Create User and assign permissions:
CREATE USER 'kk_user'@'localhost' IDENTIFIED BY 'S3cure#3214';
GRANT ALL PRIVILEGES ON kk_db.* TO 'kk_user'@'localhost';
FLUSH PRIVILEGES;

// Load / Populate Data
mysql < populate.sql
```