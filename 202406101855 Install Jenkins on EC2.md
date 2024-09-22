---
date: 2024-06-10T18:55
tags:
  - CICD
  - AWS
  - Jenkins
---
```
> ssh -i ~/.ssh/rsa ec2-user@<EC2-DNS>
> sudo yum upgrade
> sudo wget -O /etc/yum.repos.d/jenkins.repo \
    https://pkg.jenkins.io/redhat-stable/jenkins.repo
> sudo rpm --import https://pkg.jenkins.io/redhat-stable/jenkins.io-2023.key
> sudo yum upgrade
> sudo amazon-linux-extras install java-openjdk11 -y
#AMAZON LINUX 2023
> sudo dnf install java-17-amazon-corretto -y


#installing jenkins
> sudo yum install jenkins -y
> sudo systemctl enable jenkins
> sudo systemctl start jenkins
> sudo systemctl status jenkins

#installing golang
> sudo yum install go
```
