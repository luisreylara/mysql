#   All about mysql

## root on mysql
```
sudo nano /usr/local/vesta/conf/mysql.conf
sudo cat /usr/local/vesta/conf/mysql.conf
mysql -h localhost -u root -p


reate database prueba;
GRANT ALL PRIVILEGES ON prueba.* TO 'admin_default'@'%';
FLUSH PRIVILEGES;

CREATE USER ‘usuario’@‘localhost' IDENTIFIED BY 'tu_contrasena';
CREATE USER ‘usuario’@‘%’ IDENTIFIED BY ‘upjr2021;
create database lector;
GRANT ALL PRIVILEGES ON lector.* TO ‘usuario’@‘%’;

ALTER USER 'root'@'localhost' IDENTIFIED BY 'MyNewPass';

```

## WHERE IS JAVA
```
whereis java
ls -l /usr/bin/java
ls -l /etc/alternatives/java/
/usr/lib/jvm/java-11-openjdk-amd64/

```


## Cómo restablecer la contraseña de root de MySQL en Ubuntu
```
sudo service mysql stop
sudo mkdir -p /var/run/mysqld
sudo chown mysql:mysql /var/run/mysqld
sudo /usr/sbin/mysqld --skip-grant-tables --skip-networking &
mysql -u root
mysql> FLUSH PRIVILEGES;
mysql> USE mysql;
mysql> UPDATE user SET authentication_string=PASSWORD("hola2018") WHERE User='root';
mysql> UPDATE user SET plugin="mysql_native_password" WHERE User='root';
mysql> quit
sudo pkill mysqld
sudo service mysql start
```

