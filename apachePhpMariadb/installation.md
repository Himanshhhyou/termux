# Apache PHP Mariadb
## Installation 

- update and upgrade termux
```termux
pkg update && pkg upgrade
```

- install services 
```termux
pkg install apache2 php php-apache phpmyadmin mariadb
```
## Start and stop services

|Service  | Start         | Stop          |
|---------|---------------|---------------|
|apache   | httpd         | killall httpd |
|php      | php -S localhost:8082 | killall php|
|mariadb  | mysqld         | killall mysqld|

> htdocs location

```termux
cd /data/data/com.termux/files/usr/share/apache2/default-site/htdocs
```

## configure apache with php
### phpinfo();
```php
<?php
phpinfo();
?>
```
