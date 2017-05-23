# access_sql

Fix bug access denied on mac osx 10.12

1. install mysql (https://dev.mysql.com/downloads/mysql/)

2. Update password of 'root' to access.

- Open Terminal (Launchpad -> Other -> Terminal or (Command + space) -> Type 'terminal' )

- Then type follow below:

export PATH=$PATH:/usr/local/mysql/bin/

sudo mysqld_safe --skip-grant-tables

then, restart Terminal (quit then open again)

then, keep type:

export PATH=$PATH:/usr/local/mysql/bin/

mysql -u root mysql   

FLUSH PRIVILEGES;

ALTER USER 'root'@'localhost' IDENTIFIED BY '123456';

\q

sudo /usr/local/mysql/support-files/mysql.server start


- extra:

 + start mysql:
     sudo /usr/local/mysql/bin/mysqld_safe --skip-grant-tables
 + stop mysql:
     sudo /usr/local/mysql/support-files/mysql.server stop
