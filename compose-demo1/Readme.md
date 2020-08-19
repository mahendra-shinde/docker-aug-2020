## Compose demo1

1. Create a new directory "C:\compose-demo1"

2. Create "docker-compose.yml" inside "C:\compose-demo1"

```yml
version: "3.0"

services:
  app:
    image: nginx:latest
    restart: always

  db:
    image: redis:latest
    restart: always
```

3.  Use "powershell" for all the below commands

```pwsh
$ cd \compose-demo1
## Validate the compose file !
$ docker-compose config
## If entire YAML is printed back, it means NO ERROR
## Deploy the application
$ docker-compose up -d
## Check the instances running
$ docker-compose ps
## Scale your services to TWO instances each
$ docker-compose up -d --scale app=2 --scale db=2
## Check the instances running
$ docker-compose ps
## Delete all
$ docker-compose down
```