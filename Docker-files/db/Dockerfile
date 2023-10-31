FROM mysql:8.0.33
LABEL "project="vprofile"
LABEL "Author"="imran"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="accounts"

ADD db_backup.sal docker-entrypoint-initdb.d/db_backup.sql
