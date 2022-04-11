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
