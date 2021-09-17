# LAMP SERVER SETUP RELATED KNOWLEDGE

* always disable unix socket authentication

*  to add a user that can login with phpmyadmin, drop into the the mysql prompt  
  `sudo mysql`  
  and run  
  `GRANT ALL ON *.* TO 'tobecci'@'localhost' IDENTIFIED BY 'tobecci' WITH GRANT OPTION;`