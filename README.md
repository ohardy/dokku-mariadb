# PostgreSQL plugin for Dokku

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
    mariadb:console     <app>            Launch a mariadb console for a given app
    mariadb:create      <app>            Create a Mariadb database
    mariadb:delete      <app>            Delete specified Mariadb database
    mariadb:dump        <app> <filename> Dump database to SQL format
    mariadb:restore     <app> <filename> Restore database from SQL format
    mariadb:admin_console                Launch a mariadb console as admin user
    mariadb:start                        Start the Mariadb docker container if it isn't running
    mariadb:stop                         Stop the Mariadb docker container
    mariadb:status                       Shows status of Mariadb
    mariadb:list                         List all databases
```

## Usage

### Start Mariadb:
```
$ dokku mariadb:start                 # Server side
..or..
$ ssh dokku@server mariadb:start      # Client side

```

### Create a new database:
```
$ dokku mariadb:create foo            # Server side
..or..
$ ssh dokku@server mariadb:create foo # Client side
```

### Dump database to SQL:
```
$ dokku mariadb:dump foo filename.sql # Server side
```

### Restore database from SQL:
```
$ dokku mariadb:restore foo filename.sql # Server side
```
