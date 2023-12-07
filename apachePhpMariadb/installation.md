# Apache PHP Mariadb
## Installation 
To set up Apache, PHP, and MariaDB on your Termux environment, follow the step-by-step installation process outlined below.

### update and upgrade termux
Make sure your Termux packages are up to date by running the following commands:
```termux
pkg update && pkg upgrade
```
### install services
Install the required services by executing the following command:
```termux
pkg install apache2 php php-apache phpmyadmin mariadb
```
#### Start and stop services
Managing services is a crucial aspect of running a server. Familiarize yourself with the commands to start and stop Apache, PHP, and MariaDB:

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
Here i will use vim editor to edit file
so install vim by:
 ```termux
pkg install vim
```
Setting up PHP with Apache involves creating and configuring files. Follow these detailed steps:
1. Remove Default index.html
```termux
   rm index.html
```
2. Create and edit index.php
```termux
vim index.php
```
```php
<?php
phpinfo();
?>
```

### Commands for vim 
writing mode: i<br>
save Content: :wa!<br>
exit vim: :qa!<br>

### Configuration 
- edit httpd.conf file
which is inside
/data/data/com.termux/files/usr/etc/apache2
```termux
vim /data/data/com.termux/files/usr/etc/apache2/httpd.conf
```

- uncomment : **mod_mpm_prefork.so** module
comment: **mod_mpm_worker.so** module

- add libphp.so module before mod_mpm_prefork.so module
```termux
LoadModule php_module libexec/apache2/libphp.so
```
- Go to last add this line of code below <ifmodule>

```termux
#Set Handler or FilesMatch for php to understand .php file
<FilesMatch \.php$>
        SetHandler application/x-httpd-php
</FilesMatch>
```

- and add this line very last
```termux
#Load php module config file from apache2 extra directory
Include etc/apache2/extra/php_module.conf
```


- save and quit file
- go inside extra directory /data/data/com.termux/files/usr/etc/apache2/extra
  ```termux
  cd /data/data/com.termux/files/usr/etc/apache2/extra
  ```

- create a file
  ```termux
  touch php_module.conf
  ```
-all set, restart apache and php file will be run

### Set index.php default file 

go to 
```termux
vim /data/data/com.termux/files/usr/etc/apache2/httpd.conf 
```

and add index.php after index.html
```termux
<IfModule dir_module>
    DirectoryIndex index.html index.php
</IfModule>
```

  
