# Scalable-and-On-Demand-Web-Server
## Overview:
Providing auto Scalable and On-Demand web server for the users. This means, we going to deploy our web server with highly available and auto-scaling the servers to the users. This is done by using AWS resources like Launch Template, Auto Scaling Groups, and Load Balancer.

We will be creating this environment in the ap-south-1(Mumbai)region.

These are the following steps to implement our web server:
- Create a Launch Template:
- Create an Auto Scaling Group:
- Set up a Load Balancer:
- Integrate Load Balancer with Auto Scaling Group:

## Technologies:
Let's discuss the cloud technologies that are necessary for our project. The below information provides an overview of the AWS resources.
#### Launch Templates: 
A launch template is similar to a launch configuration, in that it specifies instance configuration information. It includes the ID of the Amazon Machine Image (AMI), the instance type, a key pair, security groups, and other parameters used to launch EC2 instances.
#### Auto Scaling Groups:
An Auto Scaling Group (ASG) in Amazon Web Services (AWS) is a collection of Amazon EC2 instances that are grouped together for the purpose of automatic scaling and management. ASGs are a key part of the scaling process, and they can help you maintain a desired number of instances in a group.
         
         * Note: Automatic scaling of the instance by giving some input parameters to Auto Scaling Groups:
                     - %CPU performance:  90%
                     - Max Instances:     4
                     - Min Instances:     1
                     - Desired Instances: 2

#### Load Balancer: 
Elastic Load Balancing automatically distributes your incoming traffic across multiple targets, such as EC2 instances, containers, and IP addresses, in one or more Availability Zones. It monitors the health of its registered targets, and routes traffic only to the healthy targets.

                 *Note: When we create the load balancer, we must register targets.

#### Target Groups:
A target group in AWS is a component that directs traffic to registered targets, such as EC2 instances, IP addresses, containers, or Lambda functions.

## Step 1: Launch Template
Go to the console and search for <kbd>EC2</kbd> and on. click on <kbd>Launch Templete</kbd>. Creating the new template by clicking on <kbd>Cretate Launch Templete</kbd>. follow the image below.

 ![Untitled](images/Screenshot(148)%201.png)

Set Up the launch template: These are the main requirements for deploying the server. 
- Name: <kbd>Tutorial_Website</kbd>
- Select AMI's: <kbd>Amazon Linux</kbd>
- Select Instance Type: <kbd>t2.micro</Kbd>
- Key Pair: <kbd>Ben10.pem</Kbd>
- Security Group: select SG, must allow ssh and HTTP, deny https
- Edit User Data: Copy and Past(or simply Upload the file),which must follow the correct commands and code indentation
click on the <kbd> Create Launch Template</kbd>

  ![untitled](Images/Screenshot2.png)

## Step 2: Auto Scaling Group
If we want to create an auto-scaling group, Go to select the Auto-scaling Groups on your bottom left side. and click on the <kbd>Create Auto Scaling Groups</kbd>

![untitled](Images/Screenshot3.png)

To set up the Auto Scaling Group, we need to complete the process in 7 stages:
1. Choose Launch Template:
      - Name of Auto Scaling Group: <kbd> ASGTutorialWebsite</kbd>
      - Choose Launch Template: <kbd>Tutorial_website</kbd>
2. Choose instance launch options 
