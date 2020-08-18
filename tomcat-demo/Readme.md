## Build and run this demo

1. Create a Dockerfile [refer](./Dockerfile)

2. Keep the Java applications "war" file ready in this folder.

> Or use the one provided in this repository

3. Use following command to build your image (from current directory)

```pwsh
$ docker build -t myjavaapp:1 $PWD
$ docker inspect myjavaapp:1
```

4. Create and Test a container.

```pwsh
$ docker run --name a1 -d -p 8080:8080 myjavaapp:1
```

5.  Navigate to URL `http://localhost:8080` to visit the application.

6. Clean-up

```pwsh
# docker rm -f a1
```