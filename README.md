# access_sql

ERROR 1045 (28000): Access denied for user 'root'@'localhost' (using password: YES/NO)

Fix bug access denied on macos 10.12 (Sierra)

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


3. extra:

 + start mysql:
     sudo /usr/local/mysql/bin/mysqld_safe --skip-grant-tables
 + stop mysql:
     sudo /usr/local/mysql/support-files/mysql.server stop
