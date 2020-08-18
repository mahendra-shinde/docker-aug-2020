FROM mysql:5.7

## Copy SQL file to `docker-entrypoint-initdb.d` directory
## MySQL would pick it up on startup and run all SQL commands in it!!
COPY scripts/sakila-db.sql /docker-entrypoint-initdb.d/sakila.sql

## Define usual Envs for MySQL database
ENV MYSQL_DATABASE sakila 
ENV MYSQL_USER mahendra 
ENV MYSQL_PASSWORD pass@1234 
ENV MYSQL_ROOT_PASSWORD roPass@1234

## NO CMD REQUIRED, USE CMD FROM BASE IMAGE!
