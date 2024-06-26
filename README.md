# Personal Development Environment


<h2>Description</h2>
This project repository is dedicated to tracking my journey toward becoming a cloud engineer. It showcases one of my initial projects using AWS and Terraform. As I advance in my career, 
I aim to see my development environment evolve and expand. This repository will document the steps, challenges, and learning experiences along the way.
<br />

<h2>Languages and Utilities Used</h2>

- <b>AWS</b> 
- <b>Terraform</b>
- <b>Docker</b>

<h2>Process:</h2>

<p align="center">
Current Development Environment: <br/>
<img src="https://i.imgur.com/6Pw4gL0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
</p>
Starting this dev environment in Terraform I started with creating the aws VPC by checking hashicorp official documentation and then began to provision the vpc, route table,
  internet gateway, a decault route, and route table association. I then moved on to making the security group and initially when I made the cidr blocks i put my own ip address/32
  for the ingress and egress traffic since I thought I needed it to be secure. I then created a key pair and the aws_instance I was going to put my dev node in. I then used 
  docker's documentation to write a shell script to download docker on the ec2 instance shown here:
<img src="https://i.imgur.com/HZ9zof3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  After my Terraform apply and checking my AWS console everything seemed to have deployed properly but after testing out my EC2 instance and typing in docker --version docker was not downloaded. I then double checked my script and trying to replace the instance multiple times before I realized it was a network configuration issue. I previously configured my security group to only allow my own traffic and not allow outside traffic so my instance was not able to download docker from the internet. I then changed the security group rules and voila docker is now installed into my EC2 instance and I have a fully working dev environment.
<!--

 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
