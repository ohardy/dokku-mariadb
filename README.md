# MariaDB plugin for Dokku

Project: https://github.com/progrium/dokku

## Installation

```
cd /var/lib/dokku/plugins
git clone https://github.com/ohardy/dokku-mariadb mariadb
dokku plugins-install
```


## Commands
```
$ dokku help
    mariadb:console     <app>               Launch a MariaDB console for a given app
    mariadb:env         <app>               Get generated environment variables for <app>
    mariadb:url         <app>               Get DATABASE_URL for <app>
    mariadb:create      <app>               Create a MariaDB database
    mariadb:delete      <app>               Delete specified MariaDB database
    mariadb:link        <app> <another_app> Give environment variable of database of <app> to <another_app>
    mariadb:unlink      <another_app>       Unlink <another_app> to a database
    mariadb:dump        <app> > <filename>  Dump database to SQL format
    mariadb:restore     <app> < <filename>  Restore database from SQL format
    mariadb:admin_console                   Launch a MariaDB console as admin user
    mariadb:restart                         Restart the MariaDB docker container and linked app
    mariadb:start                           Start the MariaDB docker container if it isn't running
    mariadb:stop                            Stop the MariaDB docker container
    mariadb:status                          Shows status of MariaDB
    mariadb:list                            List all databases
    mariadb:update                          Update this plugin
    mariadb:migrate                         Migrate
```

## Info
This plugin adds following environment variables to your app automatically:

* DATABASE_URL
* DB_HOST
* DB_PORT
* DB_NAME
* DB_USER
* DB_PASS

## Usage

### Start Mariadb:
```
$ dokku mariadb:start                 # Server side
..or..
$ ssh dokku@server mariadb:start      # Client side

```

### Stop Mariadb:
```
$ dokku mariadb:stop                 # Server side
..or..
$ ssh dokku@server mariadb:stop      # Client side

```

### Restart Mariadb:
```
$ dokku mariadb:restart                 # Server side
..or..
$ ssh dokku@server mariadb:restart      # Client side

```

### Create a new database:
```
$ dokku mariadb:create foo            # Server side
..or..
$ ssh dokku@server mariadb:create foo # Client side
```

### Dump database to SQL:
```
$ dokku mariadb:dump foo > filename.sql # Server side
..or..
$ ssh dokku@server mariadb:dump foo > filename.sql # Client side
```

### Restore database from SQL:
```
$ dokku mariadb:restore foo < filename.sql # Server side
..or..
$ ssh dokku@server mariadb:restore foo < filename.sql # Client side
```

### Copy database foo to database bar using pipe:
```
$ dokku mariadb:dump foo | dokku mariadb:restore bar # Server side
```


## Link
You can link a database to an application :

- Create database:
```
$ dokku mariadb:create foo
```
- Push another_app to dokku and link it to foo with:
```
$ dokku mariadb:link foo another_app
```
- Environment variables for database foo will be available in another_app

## Unlink
```
$ dokku mariadb:unlink another_app # Server side
```
