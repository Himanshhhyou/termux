# Setting Up Apache, PHP, and MariaDB on Termux

## Installation

1. **Update and Upgrade Termux:**
    ```termux
    pkg update && pkg upgrade
    ```

2. **Install Services:**
    ```termux
    pkg install apache2 php php-apache phpmyadmin mariadb
    ```

## Managing Services

| Service | Start Command               | Stop Command              |
| ------- | --------------------------- | ------------------------- |
| Apache  | `httpd`                     | `killall httpd`           |
| PHP     | `php -S localhost:8082`     | `killall php`             |
| MariaDB | `mysqld`                    | `killall mysqld`          |

> Apache's htdocs location:
> ```termux
> cd /data/data/com.termux/files/usr/share/apache2/default-site/htdocs
> ```

## Configuring Apache with PHP

### Running `phpinfo();`

1. **Navigate to Apache's htdocs:**
    ```termux
    cd /data/data/com.termux/files/usr/share/apache2/default-site/htdocs
    ```

2. **Create `index.php` and Add PHP Code:**
   Remove the existing `index.html` and create `index.php`. Add the following PHP code:
    ```php
    <?php
    phpinfo();
    ?>
    ```

Now that you've completed the setup, access PHP info by navigating to [http://localhost:8082](http://localhost:8082) in your browser.

## Additional Notes

- **Apache's Document Root:**
  The document root for Apache is where your web server looks for files to serve. In this setup, it's located at `/data/data/com.termux/files/usr/share/apache2/default-site/htdocs`.

- **Accessing PHPMyAdmin:**
  PHPMyAdmin is now installed. You can access it by navigating to [http://localhost/phpmyadmin](http://localhost/phpmyadmin) after starting the Apache and MariaDB services.

Feel free to customize and expand further based on your specific requirements!
