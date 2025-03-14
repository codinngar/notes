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