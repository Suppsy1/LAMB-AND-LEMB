# LAMB 

## Installing apache and updating the firewall

`sudo apt update` to update all the list of packages ![Sudo Apt Updste](./images/sudoapp.PNG)

`sudo apt instal apache2` to install the apache package ![Installing Apache](./images/install_apache2.1.PNG)

`sudo ufw app list` to list all currently available UFW application profiles ![UFW application profiles](./images/ufw_app_list.PNG)

`sudo ufw allow in "Apache"` to allow traffic on port 80 to allow http traffics and `sudo ufw status` to verify the changes i made ![Traffic permission and changes verifivation](./images/Traffic_permission_and_changes%20_verfication.PNG)

`sudo systemctl status apache2 ` to confrim if the apache is running as a service in our operating system ![Apache Status](./images/Apache-status.PNG)

`local host and public adress` To access the server locally and also test how our Apache HTTP server can respond to requests from the Internet ![Public Address](./images/curl-on-terminal.PNG)

On web ![public Address](./images/curl-on-web.PNG)

## Installing mysql

`sudo apt install mysql-serve` to acquire and install mysql server ![Mysql Server](./images/installing-msql.PNG) 

`sudo mysql` to login into MYSQL console ![Login](./images/logging%20in%20mysql.PNG)

`ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'PassWord.1';` setting default password ![default password](./images/change%20msql%20password.PNG)

`sudo mysql_secure_installation` Changing the default password ![default password](./images/change-password.PNG)


## Installing PHP

`sudo apt install php libapache2-mod-php php-mysql` Installing PHP ![Install PHP](./images/installing%20php.PNG)

`apt search php- | less` Installing PHP Extension ![PHP EXTENSION](./images/PHP%20EXTENSION.PNG)


## Creating a Virtual Host for my website

`sudo mkdir /var/www/projectlamp` Creating a virtual host and also creating the directory for project lamb, `sudo a2ensite projectlamp` to enable the new virtual host after creating a new configuration ![VIRTUAL HOST DOMAIN](./images/VIIRTUAL%20HOST%20DOMAIN.PNG)



`nano /var/www/your_domain/index.html` To create an index.html file in the location to test that the virtual host works as expected ![INDDEX.HTML](./images/index.html)


`http://server_domain_or_IP` To access my IP adress on web ![Hello World!](./images/HELLO%20WORLD.PNG)


`sudo nano /etc/apache2/mods-enabled/dir.conf` To allow index.php take precedence over index.html on the landing page ![Hello World!](./images/CHANGING%20THE%20BEHAVIOR%20OF%20INDEX.HTML)


## Testing PHP Processing on your Web Server

`nano /var/www/your_domain/info.php` To create a PHP test script to confirm that Apache is able to handle and process requests for PHP files ![PHP TEST!](./images/PHP%20TEST.PNG)


`http://server_domain_or_IP` Web test for PHP ![PHP test on the web](./images/PHP%20WEB.PNG)


## Testing Testing databse connection from php


`sudo mysql -p` and `mysql> SHOW DATABASES` To show the databases available on my mysql ![Mysql databases](./images/mysql%20database.PNG)


`mysql> INSERT INTO example_database.todo_list (content) VALUES ("My first important item");` and `mysql> SELECT * FROM example_database.todo_list;> SHOW DATABASES` To create Todo_list on MYSQL console ![Mysql Todo_list](./images/mysql%20todolist.PNG)




# LEMB

## Installing the Nginx web server

`sudo apt update` to update all the list of server's packages ![Sudo Apt Update](./images/SUDO_APP.PNG)

`sudo apt instal nginx` to install the nginx package ![Installing nginx](./images/install%20nginx.PNG)

`sudo ufw app list` to check the UFW profile available ![nginx list](./images/nginx%20list.PNG)

`sudo ufw allow 'Nginx HTTP` to enable port 80 and `sudo ufw status` to verify it ![Allowing port 80](./images/nginx%20allowing%20port%2080.PNG)


 `http://13.40.113.52/` to show the landing page of nginx ! [nginx landing page](./images/nginx%20landing%20page.PNG)

`sudo systemctl status apache2 ` to confrim if the apache is running as a service in our operating system ![Apache Status](./images/Apache-status.PNG)

`local host and public adress` To access the server locally and also test how our Apache HTTP server can respond to requests from the Internet ![Public Address](./images/curl-on-terminal.PNG)

On web ![public Address](./images/curl-on-web.PNG)

## Installing mysql

`sudo apt install mysql-server` to acquire and install mysql server ![Mysql Server](./images/installing%20mysql%20l.PNG) 

`sudo mysql_secure_installation` Changing the default password ![default password](./images/mysql%20default%20password.PNG)

`sudo mysql` to login into MYSQL console ![Login](./images/logging%20in%20mysql.PNG)





## Installing PHP

`sudo apt install php8.1-fpm php-mysql` Installing PHP ![Install PHP](./images/php%20installation%20for%20nginx.PNG)


## Configuring Nginx to use the PHP Processor

`sudo mkdir /var/www/your_domain` Creating a virtual host and also creating the directory for project lamb, `sudo chown -R $USER:$USER /var/www/your_domain` to assign ownership of the directory using the $USER, and `sudo nano /etc/nginx/sites-available/your_domain` to create the nano editor for Nginx sites ![VIRTUAL HOST USING NGINX](./images/nginx%20virtual%20host.PNG)


`sudo ln -s /etc/nginx/sites-available/your_domain /etc/nginx/sites-enabled/` To activate configuration by linking the configuration file, `sudo unlink /etc/nginx/sites-enabled/default` to unlink the default configuration fromthe directory, `sudo nginx -t` to check for synthax error, `sudo systemctl reload nginx` to reload nginx and  `nano /var/www/your_domain/index.html` to create the html file ![index.html](./images/nginx%20index.html)

`http://18.134.177.239/` landing page for nginx on web ![VIRTUAL HOST USING APACHE](./images/NGINX%20WEB%20LANDING%20PAGE.PNG)


## Testing PHP with Nginx

`nano /var/www/your_domain/info.php` to test PHP with Nginx ![NGINX PHP TESTING](./images/testing%20php%20with%20nginx%20result.PNG) 


`http://18.132.10.118/info.php` Web landing page for PHP with Nginx ![NGINX PHP TESTING WEB LANDING PAGE](./images/testing%20php%20with%20nginx%20WEB%20result.PNG)


## Testing Database connection from PHP

`SHOW DATABASES;` and `SELECT * FROM example_database.todo_list;`  to create database and also update the added list ![DATABASE](./images/mysql%20show%20databse%20and%20update%20database.PNG)


`nano /var/www/your_domain/todo_list.php` to connect to the MySQL database and queries for the content of the todo_list ![QUERIES FOR TODO LIST](./images/PHP%20LAST%20LAST.PNG) 

