## Container [image] registry

- Maintain "Multiple" image repositories.
- Authenticate and Authorized User Access to repositories.

### Types of Registries:
1. Hosted Registries

    Registry hosted by "Cloud Vendors". examples are 
    
    - ECR (Elastic Container Registry)
    - ACR (Azure Container Registry)
    - GCR (Google Container Registry)

2. Private (On-Premise) Registries

    The docker-registry your organization has setup on servers, and manage everything: "authentication" ,"authorization" & storage.

3.  Docker Hub (Hosted Registry)

    Docker Hub (frontend: hub.docker.com, registry: https://index.docker.io/v1)

### Using Container registries

1. `docker cli` can store multiple registry credentials at same time.

2. Use following commands with cli:

```
docker login [SERVER-URL]
docker logout [SERVER-URL]
example: 
    1. for docker-hub (default registry)
        $ docker login
        Username: [ENTER DOCKER-ID]
        Password: [ENTER PASSWORD ]
    2. for other registries (let's assume url: mahendra.azurecr.io)
        $ docker login mahendra.azurecr.io
        Username: [ENTER ADMINUSERNAME]
        Password: [PASSWORD]
```

3. Docker commands to PUSH images

```
## Re-Tag your images 
docker tag [oldimage] [newname]
# Ex:1 Push to Docker Hub
$ docker tag myapp:1 mahendrshinde/myapp:1
## Where 'mahendrshinde/' is my docker-id
$ docker push mahendrshinde/myapp:1

# Ex:2 Push to Hosted registry
$ docker tag myapp:1 mahendra.azurecr.io/myapp:1
$ docker push mahendra.azurecr.io/myapp:1
## Where, 'mahendra.azurecr.io/' is hosted registry url
```