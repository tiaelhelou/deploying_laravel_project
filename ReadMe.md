# Project - Laravel Deploy
-----------------------------

- **sudo:** allows you to temporarily elevate your current user account to have root privileges.
- **apt-get:** provides a simple way to install packages from the command line.


------------------------------------------------------------------------------------------------

### CheckPoint 1: Connecting to Server and Installing apache, php, mysql and mods
- Instal: 
        
        sudo apt-get update 
        sudo apt-get install apache2 mysql-server php-mysql php libapache2-mod-php php-mcrypt php-pear curl php-curl php-cli git

- Activate mod_rewrite:

        sudo a2enmod rewrite

- Restart apache2:

        sudo restart apache2


