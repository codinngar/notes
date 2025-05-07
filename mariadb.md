```bash
# install mariadb
sudo pacman -Sy mariadb

# initialize mariadb
sudo mariadb-install-db --user=mahmoud --basedir=/usr --datadir=/var/lib/mysql

# start and enable mariadb
sudo systemctl start mariadb
sudo systemctl enable mariadb

# run this if there is error starting mariadb
sudo chown -R mysql:mysql /var/lib/mysql
sudo chmod -R 700 /var/lib/mysql

# secure the installation
## Set a root password (recommended).
## Remove anonymous users (choose Y).
## Disallow root login remotely (choose Y unless needed).
## Remove test database (choose Y).
## Reload privilege tables (choose Y).
sudo mariadb-secure-installation

# edit user
ALTER USER 'mahmoud'@'localhost' IDENTIFIED BY 'asdf';

# after making changes ensure they take effect
FLUSH PRIVILEGES;
```