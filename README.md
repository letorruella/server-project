# Linux Server Configuration
A manual for accessing  and interacting with the server

## Getting Started

Make sure you download the ssh key.  
Login into the server `ssh name@18.222.21.241` use port 2200 `-p 2200`
If you have the key you will login successfully.

## Running the tests
Inside there is a PostgreSQL database with a flask application, you can preview the working application by going directly to the ip address `http://18.222.21.241`. 

To access the application files just head down to `/var/www/Catalog` in there you will see the app structure and it's WSGI file. In order see how the application is being serve take a look at the WSGI setup at `/etc/apache2/sites-available/Catalog.conf` 


The Postgres database has a its own user name catalog, it was created to do CRUD commands and nothing else. In the system there is a user name catalog as well which acts as the user that calls CRUD commands when the application is running instead of the user grader, this user does not have the ability to `sudo` . Run `sudo -u catalog psql`  to access the Postgres shell as catalog user.


## Software Use
* PostgreSQL
* Python 
* Apache2 
* NTP

## Configurations
  * The UFW is enable allowing only ports 2200, 80, 123
  * Custom shell command `sudo bash update.sh` that updates and upgrade which is shorter than writing `sudo apt-get...` yada yada
  * SSH port is open only 2200 and  `PermitRootLogin` is set to `no`
  * Added the ssh key to the sshd_config
  * PSQL  has user 'catalog' database for CRUD commands
  * Created a user name `grader` that has `sudo` priveldges and can change settings in the system and  `catalog`. Catalog is to handle CRUD commands from the applications this user does not have `Sudo` priviledges 


## Third party resources
[AWS Lightsail link](https://aws.amazon.com/lightsail/)
