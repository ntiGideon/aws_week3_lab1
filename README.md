## Auto Scaling Lab

Objective:

Demonstrate automatic scaling by CloudFormation to deploy an Apache web server that dynamically adjusts its capacity based on CPU load. When an instance exceeds a 50% CPU utilization threshold, the Auto Scaling Group (ASG) launches a new instance to distribute traffic. Each instance responds with its unique IP address and instance ID, verifying load distribution.

Tasks:

1. Auto Scaling Group (ASG):

a. Configuration:

i. Minimum Capacity: 1 instance

ii. Desired Capacity: 1 instance

iii. Maximum Capacity: 3 instances

b. Scaling Policy:

i. Trigger a scale-out action when the CPU utilization of an instance exceeds 50%.

2. Apache Web Server:

a. Functionality:

i. Display a message: "Hello from [IP Address] / [Instance ID]" for the instance serving the request.

ii. Include an interactive button on the webpage that, will stress test the CPU of the hosting instance, when clicked

3. Networking Setup:

a. Private Subnet:

i. Deploy the ASG within a private subnet to host the Apache web server instances securely.

b. Public Subnet:

i. Deploy an Application Load Balancer (ALB) in a public subnet using a round-robin algorithm to distribute incoming traffic across the instances.

4. Deployment Automation:

a. Use an AWS CloudFormation Git Sync to deploy resources.

b. The template will define all necessary resources (ASG, scaling policies, load balancer, subnets, etc.) and use EC2 User Data to install Apache Web Server and Web Application.
