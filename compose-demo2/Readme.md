## Compose demo 2 (DB with FrontEnd (Client))

1. Create a directory "C:\compose-demo2"

2. Create a [docker-compose.yaml](./docker-compose.yml) file inside "C:\compose-demo2"

```yml
version: '3.1'

services:

  db:
    image: mahendrshinde/mysql-sample:sakila
    restart: always
    environment:
      MYSQL_ROOT_PASSWORD: pass@123456
      MYSQL_USER: mahendra
      MYSQL_PASSWORD: password@1234

  adminer:
    image: adminer
    restart: always
    ports:
      - 8080:8080
```

3.  Deploy the application

```pwsh
$ docker-compose up -d
$ docker-compose ps
```

4.  Test application using web-browser `http://localhost:8080/`

5.  Connect using username `mahendra` and password `password@1234`

6.  Try exploring the UI, and also try any SQL queries that you know !