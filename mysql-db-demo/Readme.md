# Build MySQL Database from SQL Scripts (Schema and Data in Single file)

1. Create a folder with path "C:\mysql-demo" 

2. Download my SQL file from [here](https://raw.githubusercontent.com/mahendra-shinde/docker-aug-2020/master/mysql-db-demo/scripts/sakila-db.sql)

3. Copy the file in "C:\mysql-demo\scripts" folder.

4. Create a Dockerfile (Use VSCode for editing files) [refer](https://raw.githubusercontent.com/mahendra-shinde/docker-aug-2020/master/mysql-db-demo/Dockerfile)

```
FROM mysql:5.7

COPY scripts/sakila-db.sql /docker-entrypoint-initdb.d/sakila.sql

ENV MYSQL_DATABASE sakila 
ENV MYSQL_USER mahendra 
ENV MYSQL_PASSWORD pass@1234 
ENV MYSQL_ROOT_PASSWORD roPass@1234
```

5   Use following command to build an image and test run.

```pwsh
$ cd \mysql-demo
$ docker build -t mydb:1 $PWD
$ docker rm -f db1
$ docker run -d --name db1 mydb:1
## Wait for 4-5 minutes
$ docker logs db1
```

6. You can explore entire database using following commands:

> MySQL commandline client allows you connect local mysql database (requires user credentials).

```pwsh
$ docker exec -it db1 mysql -hlocalhost -umahendra -ppass@1234
SQL> use sakila;
SQL> show tables;
SQL> exit
$ exit
```