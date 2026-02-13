Day 3 — Docker Fundamentals, Node Deployment & Jenkins Setup

Author: Tarun Raina

📌 Overview

Day 3 focuses on building core DevOps infrastructure foundations:

Linux directory navigation & Git context switching

Installing Docker from the official repository

Running Node.js applications inside Docker containers

Hosting static websites using Nginx

Docker inspection and cleanup workflows

Jenkins installation and initial configuration

Multi-branch Git operations

This day establishes the runtime environment required for later CI/CD pipelines.

1️⃣ Directory Navigation & Repository Inspection
ls


Lists current directory contents.

cd devops_test_repo
git branch


Moves into repository and displays existing branches.

Commands were executed both inside and outside repositories to verify context.

cd ..


Returns to parent directory. Used repeatedly to switch between projects.

2️⃣ Docker Installation on Ubuntu

Docker was installed using the official Docker repository.

Update package index
sudo apt update

Install prerequisites
sudo apt install ca-certificates curl gnupg lsb-release -y

Create secure keyring directory
sudo mkdir -p /etc/apt/keyrings

Add Docker GPG key
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

Add Docker repository
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

Install Docker Engine
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

3️⃣ Docker Validation & User Permissions
Verify installation
sudo docker run hello-world

Enable non-root Docker usage
sudo usermod -aG docker $USER
newgrp docker

Test Docker without sudo
docker run hello-world

4️⃣ Node Application Setup
Clone sample Node project
git clone https://github.com/jagadeeshkanna97/docker_sample.git
cd docker_sample

Install Node dependencies
sudo apt install npm
node --version

Run application
node app.js

Install Express
npm install express
node app.js

5️⃣ Docker Image Build
docker build -t docker_sample:latest .


Builds Docker image from Dockerfile.

6️⃣ Docker Inspection & Cleanup
docker ps
docker container ls
docker ps -a
docker image ls


Cleanup:

docker rm $(docker ps -a -q)
docker rmi hello-world:latest

7️⃣ Running Node Application in Docker
docker run -p 3000:3000 --name node_app docker-sample


Detached mode:

docker run -d -p 3000:3000 --name node_app docker-sample


Container lifecycle:

docker start node_app
docker stop node_app

8️⃣ Nginx Container Deployment
docker pull nginx
docker run -d -p 80:80 --name nginx_test nginx
curl localhost
docker stop nginx_test
docker rm nginx_test

9️⃣ Hosting Static Website Using Nginx
git clone https://github.com/TarunRaina/ui-page-test.git


Run Nginx with volume mapping:

docker run -d -p 80:80 --name nginx_site -v $(pwd)/ui-page-test:/usr/share/nginx/html nginx


Verify:

curl localhost

🔟 History Logging
touch historyfile.txt
history > historyfile.txt

1️⃣1️⃣ New Git Repository — devops2
git clone https://github.com/TarunRaina/devops2.git
cd devops2
echo "#DevOps2" > README.md
git add README.md
git commit -m "Initial Commit"
git push -u origin main

1️⃣2️⃣ Jenkins Installation & Initial Configuration
Add Jenkins repository
curl -fsSL https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key | sudo tee /usr/share/keyrings/jenkins-keyring.asc > /dev/null

echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null

Install Jenkins
sudo apt update
sudo apt install openjdk-17-jdk -y
sudo apt install jenkins -y

Start Jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
sudo systemctl status jenkins


Access Jenkins:

http://<VM-IP>:8080


Retrieve admin password:

sudo cat /var/lib/jenkins/secrets/initialAdminPassword

1️⃣3️⃣ Multi-Branch Git Workflow
git checkout day1
touch day-1.txt
git rm day1.txt
git commit -m "remove day1"
git push origin day1

git add day-1.txt
git commit -m "add new day-1.txt"


Day 2:

git checkout day2
touch day-2.txt
git add day-2.txt
git commit -m "added day2 file"
git push origin day2


Day 3:

git checkout dev
git checkout -b day3
touch day-3.txt

✅ Outcome

By the end of Day 3:

Docker installed and validated

Node apps containerized

Nginx serving static content

Jenkins deployed and accessible

Multi-branch Git workflow established

This forms the operational base for CI/CD automation implemented in later stages.