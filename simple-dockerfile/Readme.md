## Dockerfile (Simple) demo

1. Create a new directory "simple-demo" in your "C:" drive.

2. Create a new file 'app.sh' inside 'simple-demo'

```bash
## Script to run
IP=$(hostname -i)
echo "$MSG from $IP"
```

3. Create another file `Dockerfile` with following contents.

```Dockerfile
FROM busybox

LABEL Author="Mahendra Shinde"
LABEL AuthorEmail="MahendraShinde@synergetics-india.com"
ENV MSG Hello World
COPY app.sh /app.sh
CMD ["/bin/sh","/app.sh"]
```

4.  Open `powershell` and use following command to build and test container image.

```pwsh
$ cd \simple-demo
$ docker build -t myapp:1 ${PWD}
## Look for Env, Cmd and Labels ...
$ docker inspect myapp:1
## Test container
$ docker run --rm -e "MSG=Hello India" myapp:1
## What is expected? 
### Hello India from 172.17.0.2
```