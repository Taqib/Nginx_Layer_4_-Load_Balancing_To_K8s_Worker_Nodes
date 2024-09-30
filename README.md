Installation of K3s and Nginx Layer 4 Load Balancing in AWS
Overview
In this lab, we will set up a lightweight Kubernetes environment using K3s on an AWS EC2 instance. Following the installation, we will configure Nginx as a Layer 4 load balancer to manage traffic to worker nodes. The services will be exposed using Kubernetes NodePort, allowing external access through Nginx.

Task Description
These are the task we will perform in this lab:
Create AWS infrastructure using PULUMI.
Create a simple flask server, build image, push to docker hub.
Configure SSH config file for SSHing into the servers.
Install and configure k3s and worker nodes.
Deploy the servers in k3s cluster.
Set up Nginx in the Nginx instance.
Test the connection using Telnet.
Test the load balancer to ensure it is working correctly.

Step by step guide
Step 1: Create AWS infrastructure using PULUMI
For this project, we need an instance for NGINX, and three instance for k3s (master-instance, worker1-instance, worker2-instance) and other necessary resouces.

Configure AWS CLI
Configure AWS CLI with the necessary credentials. Run the following command and follow the prompts to configure it:
aws configure
