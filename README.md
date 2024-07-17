# DevOps-sheet
- Author: HackBugs (YouTube Channel)

- wsl cmd
- wsl --install
- wsl --update
- wsl --list --verbose ya wsl -l -v:
- wsl -t "write name here NAME"
- wsl --shutdown
- wsl --system

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

  - Stop All Running Containers:
  - docker stop $(docker ps -q)

  - Delete All Containers (Running and Stopped):
  - docker rm $(docker ps -a -q)

  - We can use more cmd togethr with && here second comd
```sh
  - docker stop $(docker ps -q) && docker rm $(docker ps -a -q)
```

  - Delete All Containers:
  - docker rm $(docker ps -a -q)

  - Delete All Images:
  - docker rmi $(docker images -q)

  - Optional Cleanup:
  - docker system prune -a

  - systemctl status docker
  - systemctl start docker

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

- ls
- mkdir my-directory
- cd my-directory
- docker run -d -it ubuntu -Running the Container in Detached Mode 
- docker attach <container_id>
- docker ps
- docker stop <container_id>
- docker start <container_id>
- docker commit <container_id> my-ubuntu-image
- 
- docker login

# Tool list which use in Devops

ansible vs terraform
ansible vs puppet
ansible vs jenkins
ansible vs chef
ansible vs terraform vs puppet vs chef
ansible vs kubernetes
ansible vs terraform tamil
ansible vs ansible tower
ansible vs terraform hindi
ansible vs docker
ansible vscode
ansible vs helm
ansible vs nixos
ansible vs salt

--------------------------------------------------

# DevOps tools        
  docker  
  git 
  kubernetes  
  jenkins   
  terraform 
  ansible 
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

### DevOps Tools

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

### AWS Tools

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

Agar koi tool chhut gaya ho ya aur detail mein samjhna ho, to bata dena!
