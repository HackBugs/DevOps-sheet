# DevOps-sheet
- Author: HackBugs (YouTube Channel
- sudo apt-get install curl wget vim
- WSL stands for Windows Subsystem for Linux
```sh
Install WSL
---------------
wsl --install

Uninstall the current Ubuntu distribution:
-------------------------------------------
wsl --unregister Ubuntu

Update WSL:
---------------
wsl --update

Enable and Configure WSL:
------------------------------
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart

Set WSL to version 2:
-------------------------
wsl --set-default-version 2
```
- wsl cmd
- wsl --install
- wsl --update
- wsl --list --verbose ya wsl -l -v:
- wsl -t "write name here NAME"
- wsl --shutdown
- wsl --system

```sh
sudo apt-get update
sudo apt-get install docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

- Docker - Docker-Daemon
  - Docker images ubuntu, nginx, mysql, nodejs, oraclelinex, 
  - Docker --help
  - docker info
  - docker ps -show all running container list
  - docker ps -a --to this cmd can see all running and stopped containers name 
  - docker images ubuntu -can see with this cmd info of images
  - docker login
  - docker version
  - docker search ubuntu - can use image name to know more about like
  - docker search nodejs
  - ----------------------------------------------------------
  - docker image -to this cmd can see all image which you pulled
  - ----------------------------------------------------------
  - docker pull okteto/hello-world
  - docker run --hello-world
  - ----------------------------------------------------------
  - docker pull ubuntu
  - docker run -it ubuntu
  - docker run -it nginx
  - docker run -d -p 80:80 nginx
  - docker run -d -p 3306:3306 -e MYSQL_ROOT_PASSWORD=my-secret-pw mysql
  - ----------------------------------------------------------
  - app.py
  - print("Hello from Docker container!")

  - docker stop <container_id>
  - docker start <container_id>
  - docker logs <container_id>
  - exit
  - docker rm <container_id> -remove container
  - docker rm -f <container_id> -if you want to remove forcefully use -f
  - ----------------------------------------------------------
  - Stop All Running Containers:
  - docker stop $(docker ps -q)
  - ----------------------------------------------------------
  - Delete All Containers (Running and Stopped):
  - docker rm $(docker ps -a -q)
  - ----------------------------------------------------------
  - We can use more cmd togethr with && here second comd
```sh
  - docker stop $(docker ps -q) && docker rm $(docker ps -a -q)
```
  - ----------------------------------------------------------
  - Delete All Containers:
  - docker rm $(docker ps -a -q)
  - ----------------------------------------------------------
  - Delete All Images:
  - docker rmi $(docker images -q)
  - ----------------------------------------------------------
  - Optional Cleanup:
  - docker system prune -a
  - ----------------------------------------------------------
  - systemctl status docker
  - systemctl start docker
  - ----------------------------------------------------------
  - docker run -d ubuntu -if want to run in background
  - ----------------------------------------------------------
  - cd C:\my-website\
  - python -m http.server 8000

  - cd C:\my-website\
  - docker build -t my-html-website .

  - ------------------------------------------------------

docker run -it ubuntu
apt-get update
apt-get install nano
- ----------------------------------------------------------
- ls
- mkdir my-directory
- cd my-directory
- docker run -d -it ubuntu -Running the Container in Detached Mode 
- docker attach <container_id>
- docker ps
- docker stop <container_id>
- docker start <container_id>
- docker commit <container_id> my-ubuntu-image
- docker login

# Tool list which use in Devops

- ansible vs terraform
- ansible vs puppet
- ansible vs jenkins
- ansible vs chef
- ansible vs terraform vs puppet vs chef
- ansible vs kubernetes
- ansible vs terraform
- ansible vs ansible tower
- ansible vs terraform
- ansible vs docker
- ansible vscode
- ansible vs helm
- ansible vs nixos
- ansible vs salt

--------------------------------------------------

# DevOps tools 
  Linux
  git
  docker   
  kubernetes  
  jenkins   
  terraform 
  ansible 
  prometheus
  grafana
  helm  
  nginx 
  webhook
  

# AWS tools
  EC2
  ECS and ECR
  FARGATE
  LAMDA
  IAM
  RDS
  S3
  CODE commit
  server
  MONOLITH
  Grafana
  AWS EKS
  K8S cluster

----------------------------------------------------------------

Bilkul, chalo hum step-by-step in sab tools ko samjhte hain aur unka setup aur automation ka process jaan lete hain, bilkul layman language mein. 

# DevOps Tools

#### Docker
- **Kya hai?**: Docker ek tool hai jo applications ko containerize karta hai, matlab aapke application aur uske dependencies ko ek container mein pack kar deta hai. Isse application har jagah same tarah se chalti hai.
- **Install kaise kare?**
  - **Windows/Mac**: Docker Desktop download karo aur install karo.
  - **Linux**: Terminal mein yeh commands use karo:
    ```sh
    sudo apt-get update
    sudo apt-get install docker-ce docker-ce-cli containerd.io
    ```
- **Setup kaise kare?**: Docker install hone ke baad, Docker service start karo:
  ```sh
  sudo systemctl start docker
  ```
- **Automate kaise kare?**: Automation ke liye aap Dockerfile likh sakte ho jo aapke application ko containerize kar deta hai. Dockerfile ek script hota hai jo Docker container ko build karne mein help karta hai.

#### Git
- **Kya hai?**: Git ek version control system hai jo code ko track karta hai aur team collaboration ke liye use hota hai.
- **Install kaise kare?**
  - **Windows/Mac**: Git website se installer download karo aur install karo.
  - **Linux**: Terminal mein yeh command use karo:
    ```sh
    sudo apt-get install git
    ```
- **Setup kaise kare?**: Install ke baad, git ko configure karo:
  ```sh
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
  ```
- **Automate kaise kare?**: Git hooks use kar sakte ho jo automation ke liye scripts chalate hain, jaise code push hone par test run karna.

#### Kubernetes
- **Kya hai?**: Kubernetes ek container orchestration tool hai jo multiple Docker containers ko manage karta hai.
- **Install kaise kare?**: Minikube ya kubeadm use kar ke install kar sakte ho.
  - **Minikube**: 
    ```sh
    curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
    chmod +x minikube
    sudo mv minikube /usr/local/bin/
    ```
  - **kubeadm**: 
    ```sh
    sudo apt-get update && sudo apt-get install -y kubelet kubeadm kubectl
    sudo kubeadm init
    ```
- **Setup kaise kare?**: Cluster create karne ke baad, kubectl use karke manage karo.
- **Automate kaise kare?**: Helm charts use kar sakte ho jo Kubernetes applications ko package aur deploy karne mein madad karte hain.

#### Jenkins
- **Kya hai?**: Jenkins ek automation server hai jo CI/CD pipelines ko manage karta hai.
- **Install kaise kare?**:
  - **Windows/Mac**: Jenkins installer download karo aur install karo.
  - **Linux**: Terminal mein yeh commands use karo:
    ```sh
    wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
    sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
    sudo apt-get update
    sudo apt-get install jenkins
    ```
- **Setup kaise kare?**: Jenkins service start karo aur web interface (http://localhost:8080) se configure karo.
- **Automate kaise kare?**: Jenkinsfile likh sakte ho jo pipeline ko define karta hai, Jenkins automatically isko execute karta hai.

#### Terraform
- **Kya hai?**: Terraform ek infrastructure as code tool hai jo infrastructure ko automate karta hai.
- **Install kaise kare?**: 
  ```sh
  sudo apt-get update && sudo apt-get install -y gnupg software-properties-common curl
  curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
  sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
  sudo apt-get update && sudo apt-get install terraform
  ```
- **Setup kaise kare?**: Configuration file likho (main.tf) aur `terraform init` aur `terraform apply` commands use karo.
- **Automate kaise kare?**: CI/CD pipeline mein terraform commands add kar sakte ho.

#### Ansible
- **Kya hai?**: Ansible ek automation tool hai jo configuration management aur application deployment ke liye use hota hai.
- **Install kaise kare?**: 
  ```sh
  sudo apt-get update
  sudo apt-get install ansible
  ```
- **Setup kaise kare?**: Ansible playbook likho jo tasks ko define karta hai aur `ansible-playbook` command use karo.
- **Automate kaise kare?**: Jenkins pipeline mein ansible-playbook command add kar sakte ho.

  ### Prometheus

**Prometheus** ek open-source monitoring aur alerting toolkit hai jo metrics collection, storage, visualization, aur alerting ke liye use hota hai. Yeh primarily cloud-native environments aur microservices monitoring ke liye design kiya gaya hai.

#### Real-Life Example:

Imagine aap ek large scale web application operate kar rahe hain. Aapko performance metrics, server health, aur application ki overall stability monitor karna hai. Is scenario mein Prometheus ka use hota hai:

- **Metrics Collection**: Prometheus se aap apne servers, applications, databases, aur infrastructure components se metrics collect kar sakte hain.
- **Alerting**: Agar koi metric predefined threshold se upar ya niche jaata hai, to Prometheus alert generate karta hai.
- **Visualization**: Metrics ko visualize karke trends analyze kar sakte hain.

### Prometheus Install on Ubuntu:

Prometheus ko Ubuntu par install karne ke liye, aap niche diye gaye steps follow kar sakte hain:

1. **Download Prometheus**:

   ```bash
   wget https://github.com/prometheus/prometheus/releases/download/v2.34.0/prometheus-2.34.0.linux-amd64.tar.gz
   ```

2. **Extract the tarball**:

   ```bash
   tar -xvzf prometheus-2.34.0.linux-amd64.tar.gz
   ```

3. **Navigate into the extracted directory**:

   ```bash
   cd prometheus-2.34.0.linux-amd64
   ```

4. **Run Prometheus**:

   ```bash
   ./prometheus --config.file=prometheus.yml
   ```

   Yeh command Prometheus server ko start karega default configuration file `prometheus.yml` ke saath.

### Grafana

**Grafana** ek open-source analytics aur monitoring platform hai jo data ko visualize karne ke liye use hota hai. Yeh versatile dashboarding tool hai jo different data sources se data ko visualize karne mein help karta hai.

#### Real-Life Example:

Aap apne Prometheus se collect kiye gaye metrics ko visualize aur analyze karne ke liye Grafana ka use kar sakte hain:

- **Dashboard Creation**: Grafana se aap custom dashboards create kar sakte hain jismein charts, graphs, aur tables display ho.
- **Alerting**: Grafana aapko alerts set karne aur visualize metrics ke basis par actionable insights provide karne mein help karta hai.
- **Data Integration**: Multiple data sources jaise Prometheus, MySQL, AWS CloudWatch, etc., se data fetch karke Grafana mein visualize kar sakte hain.

### Grafana Install on Ubuntu:

Grafana ko Ubuntu par install karne ke liye, niche diye gaye steps follow karein:

1. **Add Grafana repository**:

   ```bash
   sudo apt-get install -y software-properties-common
   sudo add-apt-repository "deb https://packages.grafana.com/oss/deb stable main"
   ```

2. **Add Grafana GPG key**:

   ```bash
   wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
   ```

3. **Update apt packages**:

   ```bash
   sudo apt-get update
   ```

4. **Install Grafana**:

   ```bash
   sudo apt-get install grafana
   ```

5. **Start Grafana service**:

   ```bash
   sudo systemctl start grafana-server
   ```

6. **Access Grafana**:

   Open a web browser and go to `http://localhost:3000` to access Grafana. Default credentials are `admin/admin`.

### Use Cases:

- **Infrastructure Monitoring**: Server metrics, resource usage, aur performance monitoring.
- **Application Monitoring**: Application metrics, response times, aur error rates.
- **Business Analytics**: Sales data, customer analytics, aur operational metrics.

Prometheus aur Grafana ka combination aapko real-time monitoring, performance analysis, aur proactive troubleshooting mein help karta hai.

#### Helm
- **Kya hai?**: Helm ek package manager hai Kubernetes ke liye jo applications ko deploy karne mein madad karta hai.
- **Install kaise kare?**: 
  ```sh
  curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
  ```
- **Setup kaise kare?**: Helm charts likho aur `helm install` command use karo.
- **Automate kaise kare?**: CI/CD pipeline mein helm commands add kar sakte ho.

#### Nginx
- **Kya hai?**: Nginx ek web server hai jo HTTP server, reverse proxy aur load balancer ke tarah use hota hai.
- **Install kaise kare?**:
  ```sh
  sudo apt-get update
  sudo apt-get install nginx
  ```
- **Setup kaise kare?**: Configuration file `/etc/nginx/nginx.conf` edit karo aur service start karo.
- **Automate kaise kare?**: Configuration files ko Ansible playbooks se deploy kar sakte ho.

#### Webhook
- **Kya hai?**: Webhook ek HTTP callback hai jo ek event hone par trigger hota hai.
- **Setup kaise kare?**: GitHub ya Jenkins mein webhook configure karo jo specified URL ko call karta hai.
- **Automate kaise kare?**: Webhook use karke build ya deployment trigger kar sakte ho.

# AWS Tools

#### EC2
- **Kya hai?**: EC2 (Elastic Compute Cloud) AWS ka virtual server service hai.
- **Setup kaise kare?**: AWS Management Console se EC2 instance launch karo.
- **Automate kaise kare?**: Terraform ya Ansible se EC2 instances launch kar sakte ho.

#### ECS and ECR
- **Kya hai?**: ECS (Elastic Container Service) container management service hai aur ECR (Elastic Container Registry) Docker images ke liye registry hai.
- **Setup kaise kare?**: AWS Console se ECS cluster aur ECR repository create karo.
- **Automate kaise kare?**: Terraform ya Jenkins pipelines se ECS aur ECR manage kar sakte ho.

#### Fargate
- **Kya hai?**: Fargate serverless compute engine hai jo containers ko run karta hai without managing the infrastructure.
- **Setup kaise kare?**: AWS Console se Fargate tasks configure karo.
- **Automate kaise kare?**: Terraform ya Jenkins pipelines se Fargate tasks launch kar sakte ho.

#### Lambda
- **Kya hai?**: Lambda serverless compute service hai jo code ko response to events chalata hai.
- **Setup kaise kare?**: AWS Console se Lambda function create karo.
- **Automate kaise kare?**: Terraform ya AWS CLI se Lambda functions deploy kar sakte ho.

#### IAM
- **Kya hai?**: IAM (Identity and Access Management) users aur permissions manage karta hai.
- **Setup kaise kare?**: AWS Console se IAM users aur roles configure karo.
- **Automate kaise kare?**: Terraform ya AWS CLI se IAM resources manage kar sakte ho.

#### RDS
- **Kya hai?**: RDS (Relational Database Service) managed relational database service hai.
- **Setup kaise kare?**: AWS Console se RDS instance create karo.
- **Automate kaise kare?**: Terraform ya Ansible se RDS instances manage kar sakte ho.

#### S3
- **Kya hai?**: S3 (Simple Storage Service) object storage service hai.
- **Setup kaise kare?**: AWS Console se S3 bucket create karo.
- **Automate kaise kare?**: Terraform ya AWS CLI se S3 buckets manage kar sakte ho.

#### CodeCommit
- **Kya hai?**: CodeCommit AWS ka version control service hai, similar to GitHub.
- **Setup kaise kare?**: AWS Console se repository create karo.
- **Automate kaise kare?**: Jenkins ya Terraform se CodeCommit repositories manage kar sakte ho.

#### Server
- **Kya hai?**: AWS servers various types ke hote hain jaise EC2, Lightsail.
- **Setup kaise kare?**: AWS Console se servers create karo

.
- **Automate kaise kare?**: Terraform ya Ansible se servers manage kar sakte ho.

#### Monolith
- **Kya hai?**: Monolith ek large single codebase hota hai jo puri application ko encapsulate karta hai.
- **Setup kaise kare?**: Traditional deployment methods use karo.
- **Automate kaise kare?**: CI/CD pipelines use kar sakte ho automation ke liye.

#### Grafana
- **Kya hai?**: Grafana ek open-source analytics aur monitoring platform hai.
- **Install kaise kare?**:
  ```sh
  sudo apt-get install -y adduser libfontconfig1
  wget https://dl.grafana.com/oss/release/grafana_7.5.5_amd64.deb
  sudo dpkg -i grafana_7.5.5_amd64.deb
  ```
- **Setup kaise kare?**: Grafana server start karo aur web interface se configure karo.
- **Automate kaise kare?**: Configuration files use karke automation kar sakte ho.

#### AWS EKS
- **Kya hai?**: EKS (Elastic Kubernetes Service) managed Kubernetes service hai.
- **Setup kaise kare?**: AWS Console se EKS cluster create karo.
- **Automate kaise kare?**: Terraform ya AWS CLI se EKS clusters manage kar sakte ho.

#### K8s Cluster
- **Kya hai?**: K8s (Kubernetes) clusters containers ko manage karte hain.
- **Setup kaise kare?**: Minikube ya kubeadm se local clusters create karo.
- **Automate kaise kare?**: Helm charts use karke deployments automate kar sakte ho.

----------------------------------------------------------------

- # **In sab tools ko automate karne ke liye aap scripting languages jaise Bash YAML aur Python use kar sakte ho**

### Docker
- **Language for Automation**: Shell scripting (Bash), Python
- **Automation Example**: Dockerfile ka use karke application container create kar sakte ho.
  ```Dockerfile
  # Dockerfile example
  FROM python:3.8-slim-buster
  WORKDIR /app
  COPY . .
  RUN pip install -r requirements.txt
  CMD ["python", "app.py"]
  ```

### Git
- **Language for Automation**: Shell scripting (Bash), Python
- **Automation Example**: Git hooks ka use karke automation scripts likh sakte ho, jaise pre-commit hooks.
  ```sh
  # pre-commit hook script example
  # .git/hooks/pre-commit
  #!/bin/sh
  echo "Running pre-commit hook"
  pylint my_project/
  ```

### Kubernetes
- **Language for Automation**: YAML, Shell scripting (Bash), Python
- **Automation Example**: Kubernetes manifest files likh kar resources create kar sakte ho.
  ```yaml
  # Deployment YAML file example
  apiVersion: apps/v1
  kind: Deployment
  metadata:
    name: nginx-deployment
  spec:
    replicas: 3
    selector:
      matchLabels:
        app: nginx
    template:
      metadata:
        labels:
          app: nginx
      spec:
        containers:
        - name: nginx
          image: nginx:1.14.2
          ports:
          - containerPort: 80
  ```

### Jenkins
- **Language for Automation**: Groovy (Jenkinsfile), Shell scripting (Bash)
- **Automation Example**: Jenkinsfile likh kar CI/CD pipelines create kar sakte ho.
  ```groovy
  // Jenkinsfile example
  pipeline {
      agent any
      stages {
          stage('Build') {
              steps {
                  echo 'Building...'
                  sh 'make build'
              }
          }
          stage('Test') {
              steps {
                  echo 'Testing...'
                  sh 'make test'
              }
          }
          stage('Deploy') {
              steps {
                  echo 'Deploying...'
                  sh 'make deploy'
              }
          }
      }
  }
  ```

### Terraform
- **Language for Automation**: HashiCorp Configuration Language (HCL)
- **Automation Example**: Terraform configuration files likh kar infrastructure define kar sakte ho.
  ```hcl
  # Terraform configuration example
  provider "aws" {
    region = "us-west-2"
  }

  resource "aws_instance" "example" {
    ami           = "ami-0c55b159cbfafe1f0"
    instance_type = "t2.micro"
  }
  ```

### Ansible
- **Language for Automation**: YAML
- **Automation Example**: Ansible playbooks likh kar automation tasks define kar sakte ho.
  ```yaml
  # Ansible playbook example
  - hosts: servers
    tasks:
      - name: Install nginx
        apt:
          name: nginx
          state: present
  ```

### Helm
- **Language for Automation**: YAML
- **Automation Example**: Helm charts likh kar Kubernetes applications package aur deploy kar sakte ho.
  ```yaml
  # Helm chart values.yaml example
  replicaCount: 3
  image:
    repository: nginx
    tag: stable
  service:
    type: ClusterIP
    port: 80
  ```

### Nginx
- **Language for Automation**: Shell scripting (Bash), Python, YAML (for configuration management tools)
- **Automation Example**: Ansible playbook ka use karke Nginx install aur configure kar sakte ho.
  ```yaml
  # Ansible playbook to install Nginx
  - hosts: webservers
    tasks:
      - name: Ensure Nginx is installed
        apt:
          name: nginx
          state: present
      - name: Start Nginx service
        service:
          name: nginx
          state: started
          enabled: yes
  ```

### Webhook
- **Language for Automation**: Python, Shell scripting (Bash)
- **Automation Example**: Webhook server likh sakte ho jo GitHub webhook events handle kare.
  ```python
  # Simple Python webhook server example using Flask
  from flask import Flask, request

  app = Flask(__name__)

  @app.route('/webhook', methods=['POST'])
  def handle_webhook():
      data = request.json
      print(f"Received webhook event: {data}")
      return '', 200

  if __name__ == '__main__':
      app.run(port=5000)
  ```

In sab tools ko automate karne ke liye aap scripting languages jaise Bash YAML aur Python use kar sakte ho. 

----------------------------------------------------------------

Ab jab aapne Docker ko apne Ubuntu machine pe successfully install kar liya hai aur Docker service bhi start kar diya hai, to aap DevOps ke various tools ko Docker containers mein install aur use karne ke liye tayyar hain. Niche diye gaye steps follow karen:

```sh
sudo apt-get update
sudo apt-get install docker.io
sudo systemctl start docker
sudo systemctl enable docker
```

### - Steps to Install and Use DevOps Tools inside Docker on Ubuntu:

- Vi Dockerfile - inside this file Paste this script
```sh
# Use an official Node.js runtime as a parent image
FROM node:14

# Set the working directory
WORKDIR /app

# Copy package.json and package-lock.json
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Expose the port on which the app runs
EXPOSE 3000

# Command to run the application
CMD ["node", "index.js"]
```

1. **Programming Language Runtime (Node.js Example)**:
   - **Dockerfile Creation**: Node.js runtime ke liye ek Dockerfile create karein jaise maine pehle bataya tha. Dockerfile mein Node.js ko base image ke roop mein use karte hue apne application ke dependencies aur runtime environment ko setup karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/nodejs-app
     docker build -t my-nodejs-app .
     docker run -d -p 3000:3000 my-nodejs-app
     ```

2. **Database Client (MySQL Client Example)**:
   - **Dockerfile Creation**: MySQL client ke liye ek Dockerfile create karein jaise maine pehle bataya. Dockerfile mein MySQL client ko install karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/mysql-client-app
     docker build -t mysql-client .
     docker run -it --network=host mysql-client mysql -h your-mysql-host -u root -p
     ```

3. **Web Server (Nginx Example)**:
   - **Dockerfile Creation**: Nginx server ke liye ek Dockerfile create karein jaise maine pehle bataya. Dockerfile mein Nginx server ko setup karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/nginx-server-app
     docker build -t my-nginx-server .
     docker run -d -p 80:80 my-nginx-server
     ```

4. **Version Control (Git Example)**:
   - **Dockerfile Creation**: Git ko Docker container mein install karne ke liye Dockerfile mein appropriate commands add karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein.

5. **CI/CD Tools (Jenkins Example)**:
   - **Dockerfile Creation**: Jenkins server ke liye ek Dockerfile create karein jaise maine pehle bataya. Dockerfile mein Jenkins server ko setup karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/jenkins-server-app
     docker build -t my-jenkins-server .
     docker run -d -p 8080:8080 -p 50000:50000 my-jenkins-server
     ```

6. **Monitoring and Logging (Prometheus Example)**:
   - **Dockerfile Creation**: Prometheus ke liye ek Dockerfile create karein jaise maine pehle bataya. Dockerfile mein Prometheus ko setup karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/prometheus-app
     docker build -t my-prometheus-server .
     docker run -d -p 9090:9090 my-prometheus-server
     ```

7. **Configuration Management (Ansible Example)**:
   - **Dockerfile Creation**: Ansible client ke liye ek Dockerfile create karein jaise maine pehle bataya. Dockerfile mein Ansible ko setup karein.
   - **Build and Run Docker Image**: Dockerfile ko build karein aur image ko run karein, jaise:
     ```bash
     cd /path/to/your/ansible-client-app
     docker build -t ansible-client .
     docker run -it ansible-client bash

  8. **To install Kubernetes (K8s) on your system and understand its basic usage alongside Docker, follow these steps. Kubernetes is typically used for orchestrating and managing containerized applications at scale.)**:

### Installing Kubernetes (K8s)

#### Step 1: Install Docker (if not already installed)
Since you already have Docker installed, you can proceed to install Kubernetes.

#### Step 2: Install Minikube (for local Kubernetes cluster)

Minikube is a tool that runs a single-node Kubernetes cluster locally. It's ideal for learning Kubernetes and testing deployments on your local machine.

1. **Download and Install Minikube**:
   - You can download Minikube from the official GitHub repository or from the Minikube releases page.

2. **Install Minikube on Ubuntu**:
   - Open a terminal and run the following commands:

     ```bash
     curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
     sudo install minikube-linux-amd64 /usr/local/bin/minikube
     ```

     This downloads the Minikube binary and installs it into your `/usr/local/bin` directory.

3. **Start Minikube**:
   - Start Minikube with the following command:

     ```bash
     minikube start
     ```

     This command starts a single-node Kubernetes cluster locally using a virtual machine (usually VirtualBox or KVM).

4. **Verify Minikube Installation**:
   - After starting Minikube, verify its status and Kubernetes cluster configuration by running:

     ```bash
     kubectl cluster-info
     ```

     It should show you the cluster information indicating that Kubernetes is running.

### Using Kubernetes with Docker Image

Now, assuming you have a Docker image (`my-nodejs-app`) that you want to deploy and manage with Kubernetes:

#### Step 1: Create Kubernetes Deployment YAML

Create a Kubernetes Deployment YAML file (`deployment.yaml`) for deploying your Docker image (`my-nodejs-app`):

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: my-nodejs-deployment
spec:
  replicas: 1
  selector:
    matchLabels:
      app: my-nodejs-app
  template:
    metadata:
      labels:
        app: my-nodejs-app
    spec:
      containers:
        - name: my-nodejs-app
          image: my-nodejs-app
          ports:
            - containerPort: 3000
```

Save this YAML file (`deployment.yaml`) in your working directory.

#### Step 2: Deploy the Application

Apply the Deployment YAML file to create a deployment in your Minikube cluster:

```bash
kubectl apply -f deployment.yaml
```

This command creates a Kubernetes Deployment using your Docker image (`my-nodejs-app`) and exposes it on port 3000.

#### Step 3: Expose the Service

To access your application externally, expose it via a Kubernetes Service:

```bash
kubectl expose deployment my-nodejs-deployment --type=NodePort --port=3000
```

This command creates a NodePort Service that exposes your deployment on a randomly selected port on your Minikube node.

#### Step 4: Access the Application

To access your Node.js application running inside Minikube, get the URL of the Minikube cluster:

```bash
minikube service my-nodejs-deployment --url
```

This command will give you a URL where you can access your Node.js application.

### Conclusion

By following these steps, you can install Minikube to run Kubernetes locally, deploy your Dockerized Node.js application onto the Kubernetes cluster, and access it via a service exposed through Minikube. This setup helps in understanding Kubernetes basics and how it manages containerized applications. 

### Conclusion

These commands help you manage packages effectively using `apt-get` on Ubuntu and other Debian-based systems. `apt-cache` provides versatile options for searching and listing packages, making it easier to find and manage software installations.

### Conclusion:
Har DevOps tool ko Docker containers mein install karne ke liye aapko unke specific Dockerfiles create karna hoga aur fir un Dockerfiles ko build karke images ko run karna hoga. Docker containers use karke aap apne development environment ko isolated aur portable bana sakte hain, jo flexibility aur consistency provide karta hai across different environments.

----------------------------------------------------------------

### **Aap Docker container mein Ubuntu install karne ke baad uske andar kuch packages install karna chahte hain, toh aapko kuch basic steps follow karne padenge. Main aapko step-by-step batata hoon ki kaise aap Docker container ke andar packages install kar sakte hain.)**:

### Step-by-Step Guide to Install Packages in a Docker Container

1. **Docker Container Ko Start Karen**:
   Sabse pehle aapko Docker container ko start karna hoga. Aap yeh command use kar sakte hain:

   ```bash
   docker run -it ubuntu
   ```

   Is command se ek new Ubuntu container start hoga aur aap uske interactive terminal mein aa jaayenge.

2. **Update the Package List**:
   Jab aap container ke andar hain, sabse pehle package list ko update karna zaroori hai:

   ```bash
   apt-get update
   ```

3. **Install a Package**:
   Ab aap kisi bhi package ko install kar sakte hain. Example ke taur pe, agar aap `curl` install karna chahte hain, toh aap yeh command use kar sakte hain:

   ```bash
   apt-get install curl
   ```

   Aap kisi bhi package ka naam replace karke install kar sakte hain, jaise `vim`, `wget`, `python`, etc.

### Example: Installing Multiple Packages in a Docker Container

Suppose aapko curl, vim, aur git install karna hai. Aap yeh commands use karenge:

```bash
apt-get update
apt-get install -y curl vim git
```

### Dockerfile ka Use karke Packages Install Karna

Agar aap ek specific image banana chahte hain jisme required packages pre-installed ho, toh aap ek `Dockerfile` use kar sakte hain. Example ke liye, agar aap ek custom Ubuntu image create karna chahte hain jisme `curl`, `vim`, aur `git` installed hain:

1. **Create a Dockerfile**:

   Aap apne working directory mein ek `Dockerfile` create karen:

   ```Dockerfile
   # Use official Ubuntu as a parent image
   FROM ubuntu:latest

   # Update package list and install curl, vim, and git
   RUN apt-get update && apt-get install -y \
       curl \
       vim \
       git

   # Set the working directory
   WORKDIR /root

   # Default command to run when starting the container
   CMD ["bash"]
   ```

2. **Build the Docker Image**:

   Ab aapko is Dockerfile se image build karni hogi:

   ```bash
   docker build -t custom-ubuntu .
   ```

   Ye command Dockerfile ke basis pe ek new image create karega jiska naam `custom-ubuntu` hoga.

3. **Run the Docker Container**:

   Ab aap apni custom image se container run kar sakte hain:

   ```bash
   docker run -it custom-ubuntu
   ```

Is tarah se aap apne Docker container ke andar packages install kar sakte hain aur custom Docker images create kar sakte hain.
