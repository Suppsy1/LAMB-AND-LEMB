# LAMB AND LEMB

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