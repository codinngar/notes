## Installation
```bash
# update the system
sudo pacman -Syu

# install mariadb
sudo pacman -Sy mariadb

# check installation
mariadb --version

# Installing mariadb system tables
mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql

# start mysql service and check if it's running and enable it when rebooting
sudo systemctl start mariadb
sudo systemctl status mariadb
sudo systemctl enable mariadb

# secure mariadb installation 
sudo mariadb-secure-installation
# Enter current password for root (enter for none): <Enter>
# You already have your root account protected, so you can safely answer 'n'
# Switch to unix_socket authentication [Y/n] Y
# Change the root password? [Y/n] n
# Remove anonymous users? [Y/n] Y
# Disallow root login remotely? [Y/n] Y
# Remove test database and access to it? [Y/n] Y
# Reload privilege tables now? [Y/n] Y

# log into mariadb
sudo mariadb

# change password for mariadb
CREATE USER '<username>'@'localhost' IDENTIFIED BY '<password>';

# grant all privileges to the newly created user
GRANT ALL PRIVILEGES ON *.* TO '<username>'@'localhost' WITH GRANT OPTION;

# free up any cached memory and exit the MySQL client.
FLUSH PRIVILEGES;
exit
```

## Notes
```sql
-- create a database
CREATE DATABASE myDB;

-- use a database
USE myDB;

-- delete a database or a table
DROP DATABASE myDB;
DROP TABLE myTable;

-- set database as read only
ALTER DATABASE myDB READ ONLY = 1;

-- create a table with a schema
CREATE TABLE users (
	name VARCHAR(50),
    age INT,
    birth_date DATE,
    salary DECIMAL(6, 2)
);

-- return all columns from users table
SELECT * FROM users;

-- rename the table
RENAME TABLE users TO employees;

-- add a column to the table
ALTER TABLE users
ADD phone VARCHAR(15);

-- rename a column
ALTER TABLE users
RENAME COLUMN phone TO email;

-- change column data type
ALTER TABLE users
MODIFY COLUMN email VARCHAR(50);

-- change column position to be after another column or at first
ALTER TABLE users
MODIFY COLUMN email VARCHAR(50) <AFTER age | FIRST>;

-- delete a column from a table
ALTER TABLE users
DROP COLUMN email;

-- add rows to a table
INSERT INTO users
VALUES ("Ali", 32, 25000.00), (), (), ();

-- specifiy what data you want to add
INSERT INTO users (name, age)
VALUES ("Ali", 32), (), (), ();

-- return specific columns from a table
SELECT age, salary
FROM users;

-- return specific data based on a condition
SELECT *
FROM users
WHERE <age > 40 | salary IS NOT NULL>;
```

```sql
-- select columns from a table
SELECT <* | name, age | age * 20>
FROM database_name.table_name;

-- show only unique values
SELECT DISTINCT name, age
FROM database_name.table_name;

-- filter output based on a condition
SELECT *
FROM table_name
WHERE name = "Ali" AND age > 30;

-- return all names starting with Mahm and has any number of charachters after
SELECT *
FROM table_name
WHERE name LIKE "Mahm%";

-- return all names starting with Ahm and has two charachters after
SELECT *
FROM table_name
WHERE name LIKE "Ahm__";

-- return average ages, min and max for genders
SELECT gender, AVG(age), MIN(age), MAX(age)
FROM table_name
GROUP BY gender;
```