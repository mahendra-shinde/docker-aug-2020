## Container Networking

- Container networks are virtual network. And single container can connect to
    minumum ZERO to maximum ANY number of networks.

## Docker commands:

```
# List all networks
- docker network ls

# create a new network
- docker network create -n {NAME} -d {driver} --subnet {CIDR-Range}
  ex: docker network create -n net1 -d bridge --subnet 10.0.0.0/16

# delete an existing network (Must not have any containers!)
- docker network rm {NAME}
  ex: docker network rm net1

# details of given network
- docker network inspect {NAME}
  ex: docker network inspect net1
```


## Network driver "null", network name "none"

```
## First container in "none"
$ docker run --name c1 -d  --net none nginx
$ docker run --name c2 -d  --net none nginx
$ docker exec -it c1 hostname -i
$ docker exec -it c2 hostname -o
## Both containers would have no IP address
## Which means containers are NOT part of any network!
$ docker rm -f c1 c2
```

## Network driver "host", network name "host"

```
## First container in "host"
$ docker run --name c1 -d  --net host nginx
## TO AVOID port conflict using different images (tomcat uses 8080, nginx uses 80)
$ docker run --name c2 -d  --net host tomcat:8
$ docker exec -it c1 hostname -i
$ docker exec -it c2 hostname -i
## Both containers would have same IP address
## Which means containers are member of HOST network
$ docker rm -f c1 c2
```

## Network driver "bridge" network name "bridge" 

```
$ docker run --name c1 -d  --net bridge nginx
$ docker run --name c2 -d  --net bridge nginx
$ docker exec -it c1 ifconfig
$ docker exec -it c2 ifconfig
## Both containers would have different IP address
## Which means containers are member of BRIDGE network
### They can COMMUNICATE with each other 
$ docker exec -it c1 hostname -i
$ docker exec -it c2 hostname -i
## Store IP address of "c2" into Powershell Variable
$  $c2ip=$(docker exec -it c2 hostname -i)
$  docker exec -it c1 curl $c2ip
$ docker rm -f c1 c2
```
