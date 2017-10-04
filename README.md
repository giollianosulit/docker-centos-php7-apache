# Docker PHP7 + APACHE + MariaDB

This is a docker for basic PHP/MySQL Applications.
Based off latest Centos + Remi PHP Repo which has PHP 7

## Requirements
Docker - https://www.docker.com/get-docker
Composer file is built using version 2.

## Notes
This setup will have your working files stored persistently in:

```
public_html
```

which is mapped to:

```
/var/www/public_html
```

MySQL will also be mapped directly to the repository in the folder:

```
mysql
```

which is persistently mapped to:

```
/var/lib/mysql
```

Use a 3rd party app to connect to MySQL or use command line.

## Variables that need to be updated

docker-compose.yml
```
MYSQL_ROOT_PASSWORD: MYSQL_ROOT_PASSWORD
MYSQL_USER: MYSQL_ROOT_USER
MYSQL_PASSWORD: MYSQL_ROOT_PASSWORD
MYSQL_DATABASE: MYSQL_DATABASE
```

files/apache_conf/0_virtualhost.conf
```
ServerName WEB_ADDRESS
ServerAlias WEB_ADDRESS_ALIAS
ServerAdmin SERVER_ADMIN_EMAIL
```

## Getting it up and running

Here are a few basic commands to get started

### Starting the docker container (please update the settings first mentioned above)
```
docker-compose up -d
```

### Stopping Container
I recommend using STOP instead of DOWN to avoid losing any files.

* Note - Command might be different on Windows (I'm personally using OSX)
```
docker stop $(docker ps -a -q)
```

## Misc
There is a persistently mapped folder:

```
var/logs
```

Which will hold the access_logs and error_logs.

* Note this is still Work In Progress