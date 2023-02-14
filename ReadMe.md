# Project - Laravel Deploy
-----------------------------

- **sudo:** allows you to temporarily elevate your current user account to have root privileges.
- **apt-get:** provides a simple way to install packages from the command line.


--------------------------------------------------------------------------------------------------------------------------------

### CheckPoint 1: Connecting to Server and Installing apache, php, mysql and mods
- Instal: 
        
        sudo apt-get update 
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
