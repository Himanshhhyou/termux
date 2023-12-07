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

| Start  | Stop    |
|---------------|---------------|
| httpd         | killall httpd |
