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