# CI-CD-Pipeline-for-Web-App-using-Docker-Jenkins-and-AWS
For Project

CI/CD Pipeline for Web App using Docker, Jenkins, and AWS - Step-by-Step Guide
This guide will walk you through setting up a CI/CD pipeline for a Node.js web application using Jenkins, Docker, and AWS EC2. The pipeline will automate build, testing, and deployment while integrating GitHub version control and AWS CloudWatch monitoring.

Step 1: Setup AWS Infrastructure
Before setting up Jenkins and Docker, you need an AWS EC2 instance.

1.1 Create an AWS EC2 Instance

Log in to the AWS console.
Navigate to EC2 and click on Launch Instance.
Choose an Amazon Machine Image (AMI) (Ubuntu 22.04 or Amazon Linux 2 recommended).
Select an instance type (t2.medium or higher recommended).
Configure security groups:
Open ports 22 (SSH), 80 (HTTP), 443 (HTTPS), and 8080 (for Jenkins UI).
Create and download a key pair for SSH access.
Click Launch.

1.2 Connect to the EC2 Instance
```
ssh -i your-key.pem ubuntu@your-ec2-public-ip
```

Step 2: Install Jenkins on AWS EC2

2.1 Install Java (Required for Jenkins)
```
sudo apt update
sudo apt install -y openjdk-11-jdk
```
2.2 Install Jenkins
```
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
sudo sh -c 'echo deb http://pkg.jenkins.io/debian binary/ > /etc/apt/sources.list.d/jenkins.list'
sudo apt update
sudo apt install -y jenkins
```
2.3 Start and Enable Jenkins
```
sudo systemctl start jenkins
sudo systemctl enable jenkins
```



