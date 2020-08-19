# Container Orchestration

A Stack which runs on top of container platform, and offers following additional features:

1.  Service Discovery
2.  Scaling
3.  External Volumes (Persistent Volumes)

## Popular Container Orchestrators:

1. Kubernetes from "Google"

    - Already in use by "google" for last 14 years!
    - Open Source (Just like other two!)
    - Support for Windows & Linux Containers
    - Lots of third-party extensions
    - Support Any Container platform compliant with OCI (Open Container Initiative)

2. Docker Swarm from "Docker"

    - Built in "Docker" (No separate installation!)
    - Recently added support for Windows 
    - No Support for Other container platforms

3. Apache Mesos with DC/OS

    - Pure Linux environment (No Windows Containers)
    - Optimum Resource Utilization
    - Support Any Container platform compliant with OCI (Open Container Initiative)

4.  Managed Orchestrator from "Cloud Vendor" 
    example: Elastic Container Service from AWS.

    - Abstracts all cluster management tasks!
    - Scaling, Service Discovery & Volumes all services 
    - Vendor lock-in (Uses all AWS Services !)
    - Easier Setup
    - No need to learn either kubernetes, docker swarm or DC/OS!!!!