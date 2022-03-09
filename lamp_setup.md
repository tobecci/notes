# LAMP SERVER SETUP RELATED KNOWLEDGE

* always disable unix socket authentication

*  to add a user that can login with phpmyadmin, drop into the the mysql prompt  
  `sudo mysql`  
  and run  
  `GRANT ALL ON *.* TO 'tobecci'@'localhost' IDENTIFIED BY 'tobecci' WITH GRANT OPTION;`

### Mysql service cannot start

run `sudo mariadb-install-db --user=mysql --basedir=/usr --datadir=/var/lib/mysql`


## resource for changing apache2 directory

https://askubuntu.com/questions/413887/403-forbidden-after-changing-documentroot-directory-apache-2-4-6