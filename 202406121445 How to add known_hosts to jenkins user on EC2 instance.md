---
date: 2024-06-12T14:45
tags:
  - Jenkins
  - AWS
  - CICD
---
In order to access the private GitHub repository, connection should be established via ssh. A public key should be granted to GitHub and private key granted to Jenkins.

Those are the commands to generate ssh key in EC2 instance
```shell
#generating keys
> ssh-keygen -t ed25519 -C "your_email@example.com"
#starting the ssh agent
> eval "$(ssh-agent -s)"
#add private key to ssh agent 
> ssh-add ~/.ssh/id_ed25519
```

Then you should provide jenkins with `known_hosts`. It can be simply done by signing as jenkins user. But in case if you cant sign in - you can do it manually

```shell
> sudo mkdir -p /var/lib/jenkins/.ssh
> sudo ls -la /var/lib/jenkins
> sudo chmod 700 /var/lib/jenkins/.ssh
> sudo ssh-keyscan github.com | sudo tee -a /var/lib/jenkins/.ssh/known_hosts
> sudo chmod 644 /var/lib/jenkins/.ssh/known_hosts
> sudo chown -R jenkins:jenkins /var/lib/jenkins/.ssh
> sudo ls -la /var/lib/jenkins
```