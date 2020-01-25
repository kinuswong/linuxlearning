# Installation of LAMP on Debian (buster)
1. Installation of apache2
```shell
sudo apt update
sudo apt install apache2
sudo apt install ufw
sudo ufw app list
sudo ufw allow 'WWW'
sudo /etc/init.d/ufw start
sudo ufw enable
sudo ufw status
sudo systemctl status apache2
sudo hostname -I
sudo apt install curl
sudo systemctl [start | stop | restart | reload | disable | enable] apache2
```
2. Setting of virtual host
```shell
sudo mkdir -p /var/www/your_domain/html
sudo chown -R $USER:$USER /var/www/your_domain/html
sudo chmod -R 755  /var/www/your_domain
sudo touch /var/www/your_domain/html/index.html
sudo cat << EOF >/etc/apache2/sites-available/your_domain.conf
<VirtualHost *:80>
    ServerAdmin admin@your_email_domain
    ServerName your_domain
    ServerAlias www.your_domain
    DocumentRoot /var/www/your_domain/html
    ErrorLog ${APACHE_LOG_DIR}/error.log
    CustomLog ${APACHE_LOG_DIR}/access.log combined
</VirtualHost>
EOF
sudo a2ensite your_domain.conf
sudo a2dissite 000-default.conf
sudo apache2ctl configtest
sudo systemctl restart apache2
```
3. Installation of PHP
```shell
sudo apt install php7.3
sudo apt install php7.3-cli php7.3-common php7.3-curl php7.3-gd php7.3-json php7.3-mbstring php7.3-mysql php7.3-xml libapache2-mod-php7.3
php -v
```
4. Installation of ariaDB
```shell
sudo apt install mariadb-server
sudo apt install mariadb-client
sudo mysql_secure_installation
sudo mysql
```
> MariaDB [(none)]> create user newuser@localhost identified by '123456';
> MariaDB [(none)]> select user from mysql.user;
> MariaDB [(none)]GRANT ALL PRIVILEGES ON *.* TO 'Username '@'localhost' IDENTIFIED BY PASSWORD '*A69E*****ADC417AE0B8391259434A034'
> OR: 
> MariaDB [(none)]> insert into mysql.user(user, host, password) values('Username ', 'localhost', password('123456'));
> MariaDB [(none)]> flush privileges;
> $ mysql -uUsername -p

