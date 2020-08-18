## Container Volumes

Volumes provide "persistent filesystem" to number of containers.
Volumes can be RETAINED after deleting containers. Also, can be attached to multiple containers.

> Volumes are stored in host system path. Linux volumes are INACCESSIBLE on docker-desktop as it's inside Virtual machine. Use "Windows mode" instead to make them accessible.

> Please switch to "Windows Containers" before this demo.

1. Named volumes (Created prior to Containers)

```
## List all Named volumes
$ docker volume ls
## Create new...
docker volume create {NAME}
ex: docker volume create mydata
## Attach to container!
docker run -v {VOLNAME}:{GUESTPATH} [Other Options] [IMAGE-NAME] [CMD...]
ex: docker run -it -v mydata:C:\mydata --name c1 mcr.microsoft.com/windows/servercore:ltsc2019 powershell 
## Get Host Path for volume
docker volume inspect {NAME}
ex: docker volume inspect mydata
```

2. Volume binds (Created at the time of container creation)

