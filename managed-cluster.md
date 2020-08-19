# Managed Container cluster

- Cluster of containerized application managed by "vendor".
- The physical servers, networking & storage would be managed by vendor.
- AWS Elastic Container Service 
    - EC2 Instances (Virtual machines)
    - Fargate (Consumption based / serverless architecture )

## AWS ECS Cluster

1.  Login into AWS Console (URL is provided in email)

2.  Change the region to "Mumbai"

3.  Search for "ECS"  Choose "Elastic Container Service"

4.  Click "Cluster" > "Create Cluster"

    Select the first Template "AWS Fargate" then click "Next" button.

5.  Provide cluster-name (use login-id), choose option to "CREATE VPC" then click Create

> If cloud formation stack failed due to internet gateways error, try creating cluster with VPC.

6.  Select the newly created cluster, use "Add Task Definitions"

    Name of task: <USERNAME>
    Capabilities: Fargate

    Task Size:  CPU: 0.25, Memory: 0.5 GB

    Click "Add Container"
    Image: mahendrshinde/myweb
    Name: app

    Click 'Add' button

7.  Click "Create" Button, then click "View Task definition"


