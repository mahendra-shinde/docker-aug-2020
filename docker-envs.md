## Environment Variables

> Few container images REQUIRE environment variables TO BE PASSED at "run" time.

## Example: Database Containers

MySQL Database Container image:

mysql:latest, mysql:8, mysql:5.7 ....

[List of MySQL Tags](https://hub.docker.com/_/mysql?tab=tags)
 
## Creating a new MySQL Database container

Environment variables:

```yml
MYSQL_USER: mahendra
MYSQL_PASSWORD: pass@12345
MYSQL_ROOT_PASSWORD: pass@123232
MYSQL_DATABASE: data1
```

### Passing ENVs in 'docker run' (Single line, no line breaks)

```
$ docker run --name db1 -d -p 3306:3306 -e "MYSQL_USER=mahendra" -e "MYSQL_PASSWORD=pass@12345" -e "MYSQL_ROOT_PASSWORD=pass@123232" -e "MYSQL_DATABASE=data1"  mysql
## Check the DB Server logs
$ docker logs db1
$ docker stop db1
$ docker rm db1
```

### Alternate method of passing multiple envs from file (Use powershell only!)

```
## Download the env file
$ wget -usebasicparsing https://raw.githubusercontent.com/mahendra-shinde/docker-aug-2020/master/dbenvs.txt -outfile .\dbenvs.txt
$  docker run --name db1 -d -p 3306:3306 --env-file "dbenvs.txt" mysql
## Wait for 1 minute and then view logs
$ docker logs 
$ docker rm -f db1
```
