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
## Attach to container!
docker run -v {VOLNAME}:{GUESTPATH} [Other Options] [IMAGE-NAME] [CMD...]
## Get Host Path for volume
docker volume inspect {NAME}
```

### Demo: Named Volumes

1. Create a named volume

```
$ docker volume create mydata
```

2. Get information about volume (get host path)

```
$ docker volume inspect mydata
```

3.  Create a container and attach volume at guest-path (mount path) `c:\mydata` .

```
$ docker run -it -v mydata:C:\mydata --name c1 mcr.microsoft.com/windows/servercore:ltsc2019 powershell 
$ cd mydata
$ echo "Hello World" > file1.txt
$ exit
$ docker rm c1
```

4.  Create another container `c2` with the same volume.

```
$ docker run -it -v mydata:C:\mydata --name c2 mcr.microsoft.com/windows/servercore:ltsc2019 powershell 
$ cd mydata
$ type file1.txt
$ exit
```

2. Volume binds (Created at the time of container creation) [Dev Environment]

- Does not create any `named volumes`, you cannot `inspect` them.
- Allows both Host and Guest R/W Access by-default

```
docker run -v [HostPath]:[GuestPath]:[MountOption] [Other-Options] [Image-Name] [cmd...]
```

### Demo : Volume Binds

1. Create 'c:\data\index.html' file with some random HTML stuff !

2. Create and launch "IIS" container with volume binding to "C:\data" directory as "C:\inetpub\wwwroot"

```
$ docker run -d -p 8081:80 --name c1 -v c:\data:c:\inetpub\wwwroot:ro mcr.microsoft.com/windows/servercore/iis 
$ start firefox http://localhost:8081/
```

3.  Modify contents of 'c:\data\index.html' and don't forget to save the changes.

4.  repeate the following command:

```
$ start firefox http://localhost:8081
```

5. Clean-up: delete container 'c1'

