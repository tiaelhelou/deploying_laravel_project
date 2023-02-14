# Project - Laravel Deploy
-----------------------------

- **sudo:** allows you to temporarily elevate your current user account to have root privileges.
- **apt-get:** provides a simple way to install packages from the command line.


--------------------------------------------------------------------------------------------------------------------------------

### CheckPoint 1: Connecting to Server and Installing apache, php, mysql and mods
- Install:

  - Update
  
        sudo apt-get update 
        
  - Install
  
        sudo apt-get install apache2 mysql-server php-mysql php libapache2-mod-php php-mcrypt php-pear curl php-curl php-cli git

- Activate mod_rewrite:

        sudo a2enmod rewrite

- Restart apache2:

        sudo restart apache2
        
-----------------------------------------------------------------------------------------------------------------------------------

### CheckPoint 2: Getting the project from your repository
- Change Directory:

        cd var\www\html 
        
- Check Directory;

        pwd
     
- Clone Repository:

        git clone https://github.com/tiaelhelou/stunning-laravel.git
        
----------------------------------------------------------------------------------------------------------------------------------    

### CheckPoint 3: Install & Run composer

- Command Does Not Work: 

        curl -sS https://getcomposer.org/installer | sudo php — — installdir=/usr/local/bin — filename=composer
        
- Correct Command: 

        curl -sS https://getcomposer.org/installer  | sudo php --  --install-dir=/usr/local/bin --filename=composer

- Install Composer:

        sudo apt-get composer install
        
---------------------------------------------------------------------------------------------------------------------------------

### CheckPoint 4: Create .env file & generating app key

- Check Directory;

        pwd
        
- Create A Copy Of  .env.example as .env:

        cp .env.example. .env
        
- Edit .env and change the APP_NAME value to “Scripting Project”:

        vim .env
        
- Generate key:

        sudo php artisan key:generate
        
-------------------------------------------------------------------------------------------------------------------------------

### CheckPoint 5: Configure Apache

- Check If apache2 Is Installed:

        which apache2
        
- Go To apache2 Directory:

        cd /etc/apache2
        
- List All Files:

        ls
        
- Add Lines to apache2.conf:
    
  - Enter File

        vim apache2.conf
       
  - Lines
 
        <Directory /var/www/html/stunning-laravel/public>
        Options Indexes FollowSymLinks
        AllowOverride all
        Require all granted
        </Directory>
        
- Go To The “sites-enabled” Folder:

         cd sites-enabled
         
- Add Lines to “000-default.conf" After “<VirtualHost *:80>”:

  - Enter File

        vim 000-default.conf
       
  - Lines
 
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html/stunning-laravel/public/
        
- Restart apache2:

        sudo restart apache2
       
--------------------------------------------------------------------------------------------------------------------------

### CheckPoint 6: Setting folder rights & Testing website

- Go To Repository Folder:

        cd /var/www/html/stunning-laravel
        
- Change The Permissions Group For The Webserver User:

        sudo chgrp -R www-data storage bootstrap/cache
        
- Define The Writable And Executable Permission For The Webserver Owner:

        sudo chmod -R ug+rwx storage bootstrap/cache
        
-  IP Address:

        ....
-------------------------------------------------------------------------------------------------------------------------

## :tada: Congratulation Your Website Is Now Deployed :tada:
