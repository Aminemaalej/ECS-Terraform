# Resources
I will use containers based deployment with an autoscaling tool to scale the application based on CPU and Memory usage. To build this environment on AWS I used the services listed below:

* VPC and Networking (Subnets, Internet Groups...)
* Elastic Container Registry
* Elastic Container Service
* Application Load Balancer
* Auto Scaling
* Cloud Watch

# Terraform Initial Configuration
 
The first step is create a Bucket on AWS S3 to store the Terraform State. It's not required but, it'll make our life easier if someone else needs to maintain this infrastructure. This is the main.tf file with this configuration.

# VPC and Networking

We will create a VPC and configure some Networking resources we're going to use further.
For Networking, it is necessary to create Public and Private Subnets within the VPC, also a Internet Gateway and Route Tables for Public Subnets.

# Container Registry and ECS Cluster
It's time to create the Container Registry and the ECS Cluster.
The ECR is a repository where we're going store the Docker Images of the application we want to deploy.

And we're going to create the ECS Cluster, Service and Task Definition.
A service is a configuration that enables us to run and maintain a number of tasks simultaneously in a cluster. The containers are defined by a Task Definition that are used to run tasks in a service.

* Before we create the ECS Cluster, we need to create an IAM policy to enable the service to pull the image from ECR.
* Then we create the ECS Cluster
* we create a Log Group on CloudWatch to get the containers logs.
* we create a Task Definition compatible with AWS FARGATE.
* we create the ECS Service
* we defined a Security Group to avoid external connections to the containers.