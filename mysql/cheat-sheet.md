# MySQL - Cheat Sheet

## Users

#### Create user
mysql> `CREATE USER '<username>'@'localhost' IDENTIFIED BY '<password>';`

#### Drop user
mysql> `DROP USER '<username>'@'localhost';`

#### List all users
mysql> `SELECT User FROM mysql.user;`

#### Show users who has access to db
mysql> `SELECT * FROM mysql.db WHERE Db = '<database>';`


## Database

#### Create database
mysql> `CREATE DATABASE <database>;`

#### Drop database
mysql> `DROP DATABASE <database>;`

#### Associate user to database
mysql> `GRANT ALL PRIVILEGES ON <database>.* TO '<username>'@'localhost' identified by '<password>';`
