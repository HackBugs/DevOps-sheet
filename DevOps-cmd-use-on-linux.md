Categorized list of DevOps tools and their important Linux commands. This guide will help you understand what tools are used in DevOps and which Linux commands are important for each category.

### 1. **Version Control**
   - **Git**
     - `git init` - Initialize a new Git repository
     - `git clone <repo>` - Clone a repository
     - `git add <file>` - Add file changes to the staging area
     - `git commit -m "message"` - Commit changes with a message
     - `git push` - Push changes to the remote repository
     - `git pull` - Fetch and merge changes from the remote repository
     - `git branch` - List or create branches
     - `git merge <branch>` - Merge a branch into the current branch
     - `git log` - View commit history

### 2. **Continuous Integration/Continuous Deployment (CI/CD)**
   - **Jenkins**
     - `jenkins-cli.jar` - Jenkins command-line interface (requires Java)
     - `java -jar jenkins-cli.jar -s http://localhost:8080/ build <job>` - Trigger a Jenkins job
     - `java -jar jenkins-cli.jar -s http://localhost:8080/ get-job <job>` - Get job configuration
   - **GitLab CI/CD**
     - `.gitlab-ci.yml` - Configuration file for GitLab CI/CD pipelines
   - **CircleCI**
     - `.circleci/config.yml` - Configuration file for CircleCI pipelines

### 3. **Containerization**
   - **Docker**
     - `docker run` - Run a container
     - `docker ps` - List running containers
     - `docker stop <container>` - Stop a running container
     - `docker rm <container>` - Remove a stopped container
     - `docker images` - List Docker images
     - `docker rmi <image>` - Remove a Docker image
     - `docker build -t <tag> .` - Build a Docker image
     - `docker-compose up` - Start services defined in a Docker Compose file
     - `docker-compose down` - Stop and remove services defined in a Docker Compose file

### 4. **Configuration Management**
   - **Ansible**
     - `ansible-playbook <playbook>.yml` - Run an Ansible playbook
     - `ansible -m <module> -a "<args>" <host>` - Run a single Ansible module
   - **Chef**
     - `chef-client` - Run the Chef client
     - `knife` - Chef command-line tool for managing nodes, cookbooks, etc.
   - **Puppet**
     - `puppet agent -t` - Test Puppet configuration
     - `puppet apply <manifest>.pp` - Apply a Puppet manifest

### 5. **Infrastructure as Code (IaC)**
   - **Terraform**
     - `terraform init` - Initialize a Terraform configuration
     - `terraform plan` - Generate an execution plan
     - `terraform apply` - Apply the changes required to reach the desired state
     - `terraform destroy` - Destroy the Terraform-managed infrastructure
   - **CloudFormation**
     - `aws cloudformation create-stack --stack-name <name> --template-body <template>` - Create a CloudFormation stack
     - `aws cloudformation delete-stack --stack-name <name>` - Delete a CloudFormation stack

### 6. **Container Orchestration**
   - **Kubernetes**
     - `kubectl get pods` - List all pods
     - `kubectl describe pod <pod>` - Describe a pod
     - `kubectl apply -f <file>.yaml` - Apply a configuration to a resource
     - `kubectl delete pod <pod>` - Delete a pod
     - `kubectl logs <pod>` - View logs from a pod
   - **Docker Swarm**
     - `docker swarm init` - Initialize a Docker Swarm
     - `docker service create` - Create a new service in Docker Swarm
     - `docker stack deploy` - Deploy a stack to Docker Swarm

### 7. **Monitoring and Logging**
   - **Prometheus**
     - `prometheus --config.file=<config>.yml` - Start Prometheus with a configuration file
   - **Grafana**
     - `grafana-cli plugins install <plugin>` - Install a Grafana plugin
     - `grafana-server` - Start the Grafana server
   - **ELK Stack (Elasticsearch, Logstash, Kibana)**
     - `elasticsearch` - Start the Elasticsearch service
     - `logstash -f <config>.conf` - Start Logstash with a configuration file
     - `kibana` - Start the Kibana service

### 8. **Cloud Platforms**
   - **AWS CLI**
     - `aws s3 ls` - List S3 buckets
     - `aws ec2 describe-instances` - Describe EC2 instances
     - `aws iam create-user --user-name <name>` - Create an IAM user
   - **Azure CLI**
     - `az vm list` - List Azure VMs
     - `az group create --name <name> --location <location>` - Create a resource group
   - **Google Cloud CLI**
     - `gcloud compute instances list` - List Compute Engine instances
     - `gcloud app deploy` - Deploy an application to Google App Engine

### 9. **Networking**
   - **netstat**
     - `netstat -tuln` - Show active connections and listening ports
     - `netstat -r` - Show routing table
   - **ss**
     - `ss -tuln` - Display socket statistics
   - **ifconfig** (deprecated, replaced by `ip` command)
     - `ifconfig` - Display network interfaces
   - **ip**
     - `ip addr` - Display IP addresses and network interfaces
     - `ip link` - Display or modify network interfaces

### 10. **Others**
   - **Helm**
     - `helm install <chart>` - Install a Helm chart
     - `helm upgrade <release> <chart>` - Upgrade a Helm release
     - `helm delete <release>` - Delete a Helm release
   - **Nginx**
     - `nginx -t` - Test Nginx configuration
     - `nginx -s reload` - Reload Nginx configuration

Ye list aapko ek overview deti hai ki kaunse tools kis category mein aate hain aur unke important Linux commands kya hain. Har tool ke specific commands aapko documentation mein milenge jo ki specific functionalities ke liye use hote hain.
