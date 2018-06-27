# Linux Server Configuration
A manual for accessing  and interacting with the server

## Getting Started


Make sure you download the ssh  key.
Login into the server `ssh name@18.222.21.241` use port 2200 `-p 2200`
If you have the key you will successfully log into it.



## Running the tests
Inside the server is a PostgreSQL server and a flask application, you can preview the working application by going directly to the ip adress `http://18.222.21.241`. To access the application files just head down to `/var/www/Catalog` in there you will see the app structure and it's wsgi file.

The postgres server has a its own user name catalog I also created an extra user inside the server for this porpoises. Run `sudo -u catalog psql`  to access the psql shell as catalog user.


## Software Use
PostgreSQL
Python 
Apache2 
Ntp

## Configurations
  * UFW allows port 123, 80 and 2200
  * ssh port is serving on 2200 rather than 22
  * Aditional User 'catalog' used for PSQL 'catalog' database



## Third party resources
AWS Lightsail
