# Node + PHP docker structure

Notice: This is a modified version of https://github.com/laradock/laradock 
If you are interested in other container setups for PHP please look at their system.

This environment is set up with an idea of having a headless node.js framework with PHP api / admin backend.
 
# Installation
 
We expect that you are familiar with Docker basics at least to the point of having docker installed on your machine

All installation/setup steps are a recommendation and a different approach can be used if preferred.

Clone this repository alongside projects you are intending to use this for.

```
- app (for node app)
- docker (this docker repository)
- laravel (for php app)
- backend (symlink to laravel/public or the path where the backend entrypoint exists)  
```

In docker container path copy environment file. Adjust values where necessary. 
```
cp env-example .env
```
Run your containers (first time will be longer due to setup):

```
docker-compose up -d nginx mysql node-server workspace php-fpm
```

Add domain configuration to your device.

The default config uses following domain names:

- myapp.test (FE)
- backend.myapp.test (BE)

Make sure your hosts file has following lines:
```
127.0.0.1       www.myapp.test
127.0.0.1       backend.myapp.test
127.0.0.1       myapp.test
```

Hosts file is located in `/etc/hosts` on linux/unix/macos and `C:/Windows/System32/drivers/etc/hosts` on Windows devices.

# Configuration

PHP version is set to 7.4 in .env file and can be adjusted there. 

Domains are set in `nginx/sites/*.conf` - whichever .conf file(s) don't have the .example ending
Upon install this will be `node_with_php_backend.conf`. This config file sets the domain name that browser will look at.
 
   
 
