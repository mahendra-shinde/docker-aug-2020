- Building Containers using "docker-commit" then "docker-build"

- docker networking
- docker volumes
- db containers

## Containers (compared to image)
* Running instances of container images aks "images"
* Containers have IP address, can be part of container network.
* Containers have CPU/RAM allocated to them.
* Containers have an Entry-point or Command to run when they launch
* Containers have "Main" process defined by "CMD" or "EntryPoint"

```
## docker run [options] [image] [CMD/EntryPoint]
$ docker run -p 8081:80 -d nginx:alpine sh
$ wget http://localhost:8081
### You should get an error
## Run without CMD at the end (Docker would use "cmd" from image manifest )
$ docker run -p 8081:80 -d nginx:alpine 
## Test the webpage
$ wget http://localhost:8081
## You should Status 200 [OK]
## check the DEFAULT CMD inside "nginx:alpine"
$ docker inspect nginx:alpine
## Get the default CMD from Image manifest
$  docker inspect -f "{{ .Config.Cmd }}"  nginx:alpine
$ docker ps
```

* Clean-up: delete all container (force-delete)

```pwsh
$ docker rm -f $(docker ps -aq)
```
