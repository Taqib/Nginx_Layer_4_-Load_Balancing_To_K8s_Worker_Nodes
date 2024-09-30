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

Explanation: This command sets up your AWS CLI with the necessary credentials, region, and output format.

Set Up a Pulumi Project
Set Up a Pulumi Project:
Create a new directory for your project and navigate into it:

mkdir aws-k3s-infra
cd aws-k3s-infra

Initialize a New Pulumi Project:
Run the following command to create a new Pulumi project:

pulumi new aws-javascript

Create Key Pair::
Nginx Instance
aws ec2 create-key-pair --key-name nginx --query 'KeyMaterial' --output text > nginx.pem

k3s cluster
aws ec2 create-key-pair --key-name k3sCluster --query 'KeyMaterial' --output text > k3sCluster.pem

These commands will create key pair for nginx instance and for k3s cluster(master, worker1, worker2)

Set File Permissions of the key files:

chmod 400 nginx.pem
chmod 400 k3sCluster.pem


Write Code for infrastructure creation
Open index.js file in your project directory:


Step 2: Create a simple flask server, build image, push to docker hub
Create a directory in your local machine (e.g., flask-server)






