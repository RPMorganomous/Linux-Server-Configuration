<<<<<<< HEAD
# Classic Rock Hall Of Fame Catalog

## Main technologies and methodologies implemented:
* Python 2.7
* Flask
* Bootstrap
* SQLAlchemy
* sqlite
* JSON
* CRUD
* HTML
* CSS
* OAuth
* Vagrant Virtual Machine
* Google API
* Facebook API

### This catalog project is a Python module that uses an sqlite database to manage bands and albums from the classic rock genre.  The purpose of this project is to demonstrate aptitude with Create Read Update and Delete database functionality.

The program is tested by executing project.py.  If all goes well, when you open your browser and point to localhost:8000 you will see this:

![alt tag](https://github.com/RPMorganomous/catalog/blob/master/static/screenshot.png)

# Follow These Steps To Test The Program
(I'm assuming you already have python2.7 installed)

### Install Virtualbox
https://www.virtualbox.org/wiki/Downloads

### Install Vagrant
https://www.vagrantup.com/downloads

Verify that Vagrant is installed and working by typing in the terminal:

    $ vagrant -v   # will print out the Vagrant version number

### Clone the Repository

If you don't already have Git installed, [download Git from git-scm.com.](http://git-scm.com/downloads) Install the version for your operating system.

On Windows, Git will provide you with a Unix-style terminal and shell (Git Bash).  
(On Mac or Linux systems you can use the regular terminal program.)

You will need Git to install the configuration for the VM. If you'd like to learn more about Git, [take a look at our course about Git and Github](http://www.udacity.com/course/ud775).

Once you are sure that VirtualBox and Vagrant are installed correctly execute the following:

    $ git clone https://github.com/RPMorganomous/catalog.git
    $ cd vagrant
    $ cd catalog

### Verify that these files exist in the newly cloned repository:

    --catalog                    #folder containing tournament files
    ----project.py               #file that contains the python functions which 
                                    unit tests will run on
    ----band_database_setup.py   #unit tests for tournament.py
    ----bandalbumswithusers.db   #sqlite database
    --Vagrantfile                #template that launches the Vagrant environment
    --pg_config.sh               #shell script provisioner called by Vagrantfile
                                    that performs configurations

### Launch the Vagrant Box

VirtualBox is the software that actually runs the VM. [You can download it from virtualbox.org, here.](https://www.virtualbox.org/wiki/Downloads)  Install the *platform package* for your operating system.  You do not need the extension pack or the SDK. You do not need to launch VirtualBox after installing it.

**Ubuntu 14.04 Note:** If you are running Ubuntu 14.04, install VirtualBox using the Ubuntu Software Center, not the virtualbox.org web site. Due to a [reported bug](http://ubuntuforums.org/showthread.php?t=2227131), installing VirtualBox from the site may uninstall other software you need.

    $ vagrant up   #to launch and provision the vagrant environment
    $ vagrant ssh  #to login to your vagrant environment
    
Vagrant is the software that configures the VM and lets you share files between your host computer and the VM's filesystem.  [You can download it from vagrantup.com.](https://www.vagrantup.com/downloads) Install the version for your operating system.

**Windows Note:** The Installer may ask you to grant network permissions to Vagrant or make a firewall exception. Be sure to allow this.

From the terminal, run:

    git clone https://github.com/udacity/OAuth2.0 oauth

This will give you a directory named **oauth** complete with the source code for the flask application, a vagrantfile, and a bootstrap.sh file for installing all of the necessary tools. 

## Run the virtual machine!

Using the terminal, change directory to oauth (**cd oauth**), then type **vagrant up** to launch your virtual machine.

### Change Directory To The Catalog Directory

    $ cd /
    $ cd vagrant
    $ cd catalog

### Initialize the database

(Optional unless you want to use the pre-configured database.  Otherwise, you can delete bandalbumswithusers.db and recreate it using the following commands)

    $ python band_database_setup.py     #creates the database
    $ python lotsofalbums.py            #import a dummy user and the first three bands with albums into the database 
                                        (note that if you wish to have permission to edit these three, you must run the
                                        server and log in using the next steps BEFORE importing the database)
You should see this result:

    Bands and albums successfully imported!

### Run the application

    $ python project.py

    Open your browser and point to localhost:8000
    Use the LOGIN option at the upper right of your screen to log in using Google or Facebook.  Upon first login you will
    be added as a new user with permission to edit any bands or albums you create.
    
### JSON output

    This application will produce JSON files by directing your browser to the following urls:
    /band/<int:band_id>/albums/JSON for all albums by a specific band
    /album/<int:album_id>/JSON for a specific album
    /albums/JSON for all albums in the db
    /bands/JSON for all bands in the db

### Shutdown the application

    ctrl+C

### Shutdown Vagrant machine

    $ vagrant halt


### Destroy the Vagrant machine

    $ vagrant destroy

### Coming Soon - UPGRADES
* More detail on bands and albums
* Gear and performance tips to reproduce the music you love
* Option to order the albums from Amazon.com
=======
# Linux-Server-Configuration
Baseline installation of a Linux distribution on a virtual machine prepared to host web applications, including installed updates, secured from a number of attack vectors and installed/configured web and database servers.

IP address: 184.73.104.22
SSH port: 2200
Complete URL: http://ec2-184-73-104-22.compute-1.amazonaws.com/

# Hosting Configuration Project Summary:

## Overview:
In order to host a previous Flask project application ([Classic Rock Hall of Fame](https://github.com/RPMorganomous/catalog)) from a github clone, an Amazon Lightsail server has been configured with Ubuntu to host the project on SSH port 2200.  Apache has been installed and configured to serve a Python mod_wsgi application.  A Postgresql database has been installed and initialized.  The Postgresql database was substituted for the sqlite database and minior changes in the original code were required.  A new virtual host has been enabled using Flask.  Accounts have been created for management of the db and to allow user access for review purposes.

## Steps and Instructions:

## Tasks
1. Create an Amazon Lightsail account configured with Ubuntu
2. Follow the instructions provided to SSH into your server
3. Create a new user named grader
4. Give the grader the permission to sudo
5. Update all currently installed packages
6. Change the SSH port from 22 to 2200
7. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80)
8. Configure the local timezone to UTC
9. Install and configure Apache to serve a Python mod_wsgi application
10. Install and configure PostgreSQL:
	- Do not allow remote connections
	- Create a new user named catalog that has limited permissions to your catalog application database
11. Install git, clone and setup your Catalog App project (from your GitHub repository from earlier in the Nanodegree program) so that it functions correctly when visiting your server’s IP address in a browser. Remember to set this up appropriately so that your .git directory is not publicly accessible via a browser!

## Launch Virtual Machine

## Instructions for SSH access to the instance
1. Download Private Key
2. Move the private key file into the folder `~/.ssh` (where ~ is your environment's home directory). So if you downloaded the file to the Downloads folder, just execute the following command in your terminal.
	```mv ~/Downloads/LightsailDefaultPrivateKey.pem ~/.ssh/```
3. Open your terminal and type in
	```chmod 600 ~/.ssh/LightsailDefaultPrivateKey.pem```
4. In your terminal, type in
	```ssh -i ~/.ssh/LightsailDefaultPrivateKey.pem root@184.73.104.22```
5. Development Environment Information

	Public IP Address

	184.73.104.22
	
	Private Key ( is not provided here. )

## Create a new user named grader
1. `sudo adduser grader`
2. `vim /etc/sudoers`
3. `touch /etc/sudoers.d/grader`
4. `vim /etc/sudoers.d/grader`, type in `grader ALL=(ALL:ALL) ALL`, save and quit

## Set ssh login using keys
1. generate keys on local machine using`ssh-keygen` ; then save the private key in `~/.ssh` on local machine
2. deploy public key on developement enviroment

	On you virtual machine:
	```
	$ su - grader
	$ mkdir .ssh
	$ touch .ssh/authorized_keys
	$ vim .ssh/authorized_keys
	```
	Copy the public key generated on your local machine to this file and save
	```
	$ chmod 700 .ssh
	$ chmod 644 .ssh/authorized_keys
	```
	
3. reload SSH using `service ssh restart`
4. now you can use ssh to login with the new user you created

	`ssh -i [privateKeyFilename] grader@184.73.104.22`

## Update all currently installed packages

	sudo apt-get update
	sudo apt-get upgrade

## Change the SSH port from 22 to 2200
1. Use `sudo vim /etc/ssh/sshd_config` and then change Port 22 to Port 2200 , save & quit.
2. Reload SSH using `sudo service ssh restart`

## Configure the Uncomplicated Firewall (UFW)

Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80)

	sudo ufw allow 2200/tcp
	sudo ufw allow 80/tcp
	sudo ufw enable 
 
## Configure the local timezone to UTC
1. Configure the time zone `sudo dpkg-reconfigure tzdata`
2. It is already set to UTC.

## Install and configure Apache to serve a Python mod_wsgi application
1. Install Apache `sudo apt-get install apache2`
2. Install mod_wsgi `sudo apt-get install python-setuptools libapache2-mod-wsgi`
3. Restart Apache `sudo service apache2 restart`

## Install and configure PostgreSQL
1. Install PostgreSQL `sudo apt-get install postgresql`
2. Check if no remote connections are allowed `sudo vim /etc/postgresql/9.3/main/pg_hba.conf`
3. Login as user "postgres" `sudo su - postgres`
4. Get into postgreSQL shell `psql`
5. Create a new database named catalog  and create a new user named catalog in postgreSQL shell
	
	```
	postgres=# CREATE DATABASE bandalbumswithusers;
	postgres=# CREATE USER catalog;
	```
5. Set a password for user catalog
	
	```
	postgres=# ALTER ROLE catalog WITH PASSWORD 'password';
	```
6. Give user "catalog" permission to "catalog" application database
	
	```
	postgres=# GRANT ALL PRIVILEGES ON DATABASE catalog TO catalog;
	```
7. Quit postgreSQL `postgres=# \q`
8. Exit from user "postgres" 
	
	```
	exit
	```
 
## Install git, clone and setup your Catalog App project.
1. Install Git using `sudo apt-get install git`
2. Use `cd /var/www` to move to the /var/www directory 
3. Create the application directory `sudo mkdir CatalogApp/CatalogApp`
4. Move inside this directory using `cd CatalogApp`
5. Clone the Catalog App to the virtual machine `git clone https://github.com/RPMorganomous/catalog.git`
6. Rename the project's name `sudo mv ./catalog ./CatalogApp`
7. Move to the inner CatalogApp directory using `cd CatalogApp`
8. Rename `project.py` to `__init__.py` using `sudo mv project.py __init__.py`
9. Edit `band_database_setup.py`, `lotsofalbums.py` and change `engine = create_engine('sqlite:///toyshop.db')` to `engine = create_engine('postgresql://catalog:password@localhost/catalog')`
10. Install pip `sudo apt-get install python-pip`
11. Use pip to install dependencies `sudo pip install -r requirements.txt`
12. Install psycopg2 `sudo apt-get -qqy install postgresql python-psycopg2`
13. Create database schema `sudo python band_database_setup.py`

## Configure and Enable a New Virtual Host
1. Create CatalogApp.conf to edit: `sudo nano /etc/apache2/sites-available/CatalogApp.conf`
2. Add the following lines of code to the file to configure the virtual host. 
	
	```
	<VirtualHost *:80>
		ServerName 184.73.104.22
		ServerAdmin mba.rick@gmail.com
		WSGIScriptAlias / /var/www/CatalogApp/catalogapp.wsgi
		<Directory /var/www/CatalogApp/CatalogApp/>
			Order allow,deny
			Allow from all
		</Directory>
		Alias /static /var/www/CatalogApp/CatalogApp/static
		<Directory /var/www/CatalogApp/CatalogApp/static/>
			Order allow,deny
			Allow from all
		</Directory>
		ErrorLog ${APACHE_LOG_DIR}/error.log
		LogLevel warn
		CustomLog ${APACHE_LOG_DIR}/access.log combined
	</VirtualHost>
	```
3. Enable the virtual host with the following command: `sudo a2ensite CatalogApp`

## Create the .wsgi File
1. Create the .wsgi File under /var/www/CatalogApp: 
	
	```
	cd /var/www/CatalogApp
	sudo nano catalogapp.wsgi 
	```
2. Add the following lines of code to the catalogapp.wsgi file:
	
	```
	#!/usr/bin/python
	import sys
	import logging
	logging.basicConfig(stream=sys.stderr)
	sys.path.insert(0,"/var/www/CatalogApp/")

	from CatalogApp import app as application
	application.secret_key = 'Add your secret key'
	```

## Restart Apache
1. Restart Apache `sudo service apache2 restart `

## References:
https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
>>>>>>> 7d637c3aae172bf0072de4995e48111db66349cf

