# Apache PHP Mariadb installation

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
|php   | php -S localhost:8082 | killall php |

|mariadb   | mysqld         | killall mysqld |
