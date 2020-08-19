## Docker Compose

- Declarative method for deploying / managing multi-container applications
- uses YAML (internally converts into JSON)
- Automation ready !
- Supports docker-swarm or kubernetes (docker-deskop)

## Components defines in `docker-compose` file

1. Services:    A Wrapper for containers. The first container (instance) of service is always given a name
        [servicename]_1. The second instance would be [servicename]_2 ....

2.  Volumes:    Named volumes attached to one or more containers.

3.  Networks:   One or more networks used by containers. There is always a "default" network.

## Few commands.

> docker-compose assumes there is either "docker-compose.yaml" or "docker-compose.yml" present in current directory.

```
docker-compose version
# Validate the YAML file.
docker-compose config
# create or update all resources (services, networks & volumes)
docker-compose up 
# down all resources (services, networks & volumes)
docker-compose down
# List all containers / service instances 
docker-compose ps
```

