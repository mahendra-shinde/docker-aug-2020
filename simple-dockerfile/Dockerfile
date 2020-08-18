## The filename is "Case-Sensitive" 
## File uses NO EXTENSION
## Default filename: "Dockerfile"

## Define the BASE IMAGE
FROM busybox

## OPTIONAL VALUES TOBE STORED IN IMAGE MANIFEST
LABEL Author="Mahendra Shinde"
LABEL AuthorEmail="MahendraShinde@synergetics-india.com"

## Define environment variables
ENV MSG Hello World

## Copy few files from HOST (Present Working Directory!) to GUEST
COPY app.sh /app.sh

## Define the COMMAND to Launch at Startup
CMD ["/bin/sh","/app.sh"]
