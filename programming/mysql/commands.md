# Mysql commands

## log in

`[mysql shell> mysql -h localhost -u [username] -p[password]`

## show database tables

`[mysql shell> SHOW DATABASES`

## select a database table

`[mysql shell> USE [table name]`

## Backup Databases

`$ mysqldump -u [username] -p[password] [database name] > [filename].sql`

## Restore database from file

`mysql -u [user] -p [database_name] < [filename].sql`

