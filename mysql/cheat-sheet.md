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

#### Assign PROCESS privilege for user to database
mysql> `GRANT PROCESS ON *.* to '<username>'@'localhost';`


## Database

#### Create database
mysql> `CREATE DATABASE <database>;`

#### Drop database
mysql> `DROP DATABASE <database>;`

#### Associate user to database

##### Mysql
mysql> `GRANT ALL PRIVILEGES ON <database>.* TO '<username>'@'localhost' IDENTIFIED BY '<password>';`

##### MariaDB
mysql> `GRANT ALL ON <database>.* TO '<username>'@'localhost';`

#### Import sql dump into database
mysql> `mysql -u <username> -p -h localhost <database> < data.sql`

#### Export database
mysql> `mysqldump -u <username> -p -h localhost <database> > data.sql`
