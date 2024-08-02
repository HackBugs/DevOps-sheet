### 1. **Ansible**
1. **Update Ubuntu**:
   ```bash
   sudo apt update
   sudo apt upgrade
   ```

2. **Install Ansible**:
   ```bash
   sudo apt install ansible
   ```

3. **Verify Installation**:
   ```bash
   ansible --version
   ```

### 2. **Jenkins**
1. **Install Java** (Jenkins requires Java):
   ```bash
   sudo apt update
   sudo apt install openjdk-11-jdk
   ```

2. **Add Jenkins Repository**:
   ```bash
   wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
   sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
   ```

3. **Install Jenkins**:
   ```bash
   sudo apt update
   sudo apt install jenkins
   ```

4. **Start Jenkins**:
   ```bash
   sudo systemctl start jenkins
   ```

5. **Enable Jenkins to Start at Boot**:
   ```bash
   sudo systemctl enable jenkins
   ```

6. **Access Jenkins**:
   Open your browser and go to `http://localhost:8080` to complete the setup.

### 3. **Kubernetes**
1. **Install Docker** (Kubernetes uses Docker):
   ```bash
   sudo apt update
   sudo apt install docker.io
   sudo systemctl start docker
   sudo systemctl enable docker
   ```

2. **Install kubeadm, kubelet, and kubectl**:
   ```bash
   sudo apt update && sudo apt install -y apt-transport-https ca-certificates curl
   curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
   sudo sh -c 'echo deb http://apt.kubernetes.io/ kubernetes-xenial main > /etc/apt/sources.list.d/kubernetes.list'
   sudo apt update
   sudo apt install -y kubelet kubeadm kubectl
   ```

3. **Initialize Kubernetes Cluster**:
   ```bash
   sudo kubeadm init
   ```

4. **Set Up Local kubeconfig**:
   ```bash
   mkdir -p $HOME/.kube
   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   sudo chown $(id -u):$(id -g) $HOME/.kube/config
   ```

5. **Install a Network Plugin** (e.g., Flannel):
   ```bash
   kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml
   ```

### 4. **Terraform**
1. **Download Terraform**:
   ```bash
   wget https://releases.hashicorp.com/terraform/1.5.5/terraform_1.5.5_linux_amd64.zip
   ```

2. **Unzip and Install**:
   ```bash
   unzip terraform_1.5.5_linux_amd64.zip
   sudo mv terraform /usr/local/bin/
   ```

3. **Verify Installation**:
   ```bash
   terraform --version
   ```

### 5. **Chef**
1. **Install Chef Workstation**:
   ```bash
   wget https://packages.chef.io/files/stable/chef-workstation/23.6.10/debian/11/chef-workstation_23.6.10-1_amd64.deb
   sudo dpkg -i chef-workstation_23.6.10-1_amd64.deb
   ```

2. **Verify Installation**:
   ```bash
   chef --version
   ```

### 6. **Nagios**
1. **Install Dependencies**:
   ```bash
   sudo apt update
   sudo apt install -y wget build-essential libgd-dev libapache2-mod-php php-gd
   ```

2. **Download and Install Nagios Core**:
   ```bash
   wget https://github.com/NagiosEnterprises/nagioscore/archive/refs/tags/4.4.6.tar.gz
   tar xzf 4.4.6.tar.gz
   cd nagioscore-4.4.6
   ./configure
   make all
   sudo make install
   sudo make install-init
   sudo make install-commandmode
   sudo make install-config
   sudo make install-webconf
   ```

3. **Create Nagios Admin User**:
   ```bash
   sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin
   ```

4. **Start Nagios**:
   ```bash
   sudo systemctl start nagios
   sudo systemctl enable nagios
   ```

5. **Access Nagios**:
   Open your browser and go to `http://localhost/nagios` to access the Nagios web interface.

### 7. **Docker**
1. **Install Docker**:
   ```bash
   sudo apt update
   sudo apt install docker.io
   ```

2. **Start Docker**:
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   ```

3. **Verify Installation**:
   ```bash
   docker --version
   ```
   __________________________________________________________________________________________________________________________________________________________________________________________________________

### 1. **Ansible**

**Installation Steps:**
1. **Update your system:**
   ```bash
   sudo apt update
   sudo apt upgrade
   ```

2. **Install Ansible:**
   ```bash
   sudo apt install ansible
   ```

3. **Verify Installation:**
   ```bash
   ansible --version
   ```

**Main Files:**
- **Hosts File (`/etc/ansible/hosts`):** Yeh file define karti hai ki kaunse servers Ansible ke saath manage kiye jayenge.
- **Playbook (`playbook.yml`):** Yeh YAML file tasks aur configurations define karti hai jo Ansible run karta hai.

**Example Hosts File:**
   ```ini
   [web]
   192.168.1.1
   192.168.1.2
   
   [db]
   192.168.1.3
   ```

**Example Playbook:**
   ```yaml
   - name: Install Nginx
     hosts: web
     tasks:
       - name: Install nginx
         apt:
           name: nginx
           state: present
   ```

### 2. **Jenkins**

**Installation Steps:**
1. **Add Jenkins Repository:**
   ```bash
   wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
   sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary > /etc/apt/sources.list.d/jenkins.list'
   ```

2. **Install Jenkins:**
   ```bash
   sudo apt update
   sudo apt install jenkins
   ```

3. **Start Jenkins Service:**
   ```bash
   sudo systemctl start jenkins
   sudo systemctl enable jenkins
   ```

4. **Access Jenkins:** Open a browser and go to `http://localhost:8080`.

### 3. **Kubernetes**

**Installation Steps:**
1. **Install `kubeadm`, `kubelet`, and `kubectl`:**
   ```bash
   sudo apt update
   sudo apt install -y apt-transport-https ca-certificates curl
   curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
   sudo sh -c 'echo "deb https://apt.kubernetes.io/ kubernetes-xenial main" > /etc/apt/sources.list.d/kubernetes.list'
   sudo apt update
   sudo apt install -y kubelet kubeadm kubectl
   sudo apt-mark hold kubelet kubeadm kubectl
   ```

2. **Initialize Kubernetes Master:**
   ```bash
   sudo kubeadm init
   ```

3. **Configure kubectl:**
   ```bash
   mkdir -p $HOME/.kube
   sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
   sudo chown $(id -u):$(id -g) $HOME/.kube/config
   ```

4. **Install a Network Plugin (e.g., Calico):**
   ```bash
   kubectl apply -f https://docs.projectcalico.org/manifests/calico.yaml
   ```

### 4. **Terraform**

**Installation Steps:**
1. **Download Terraform:**
   ```bash
   wget https://releases.hashicorp.com/terraform/1.4.5/terraform_1.4.5_linux_amd64.zip
   ```

2. **Unzip and Move to `/usr/local/bin`:**
   ```bash
   unzip terraform_1.4.5_linux_amd64.zip
   sudo mv terraform /usr/local/bin/
   ```

3. **Verify Installation:**
   ```bash
   terraform --version
   ```

**Main Files:**
- **Configuration File (`main.tf`):** Yeh file Terraform ko batata hai ki kya infrastructure create karna hai.

**Example Configuration:**
   ```hcl
   provider "aws" {
     region = "us-west-2"
   }

   resource "aws_instance" "example" {
     ami           = "ami-12345678"
     instance_type = "t2.micro"
   }
   ```

### 5. **Chef**

**Installation Steps:**
1. **Install Chef Workstation:**
   ```bash
   wget https://packages.chef.io/files/stable/chef-workstation/24.5.441/debian/10/chef-workstation_24.5.441-1_amd64.deb
   sudo dpkg -i chef-workstation_24.5.441-1_amd64.deb
   ```

2. **Verify Installation:**
   ```bash
   chef --version
   ```

**Main Files:**
- **Cookbook:** Yeh directory jisme recipes aur configurations hoti hain.
- **Chef Recipe (`default.rb`):** Yeh Ruby file hai jo system configuration specify karti hai.

**Example Recipe:**
   ```ruby
   package 'nginx' do
     action :install
   end

   service 'nginx' do
     action [:enable, :start]
   end
   ```

### 6. **Nagios**

**Installation Steps:**
1. **Install Dependencies:**
   ```bash
   sudo apt update
   sudo apt install -y autoconf gcc libgd-dev make apache2 php libapache2-mod-php
   ```

2. **Download and Install Nagios Core:**
   ```bash
   wget https://sourceforge.net/projects/nagios/files/latest/download -O nagios.tar.gz
   tar -xzf nagios.tar.gz
   cd nagios-*
   sudo ./configure --with-httpd-conf=/etc/apache2/sites-enabled
   sudo make all
   sudo make install
   sudo make install-init
   sudo make install-commandmode
   sudo make install-config
   sudo make install-webconf
   ```

3. **Create Nagios Admin User:**
   ```bash
   sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin
   ```

4. **Start Nagios:**
   ```bash
   sudo systemctl start nagios
   sudo systemctl enable nagios
   ```

5. **Access Nagios:** Open a browser and go to `http://localhost/nagios`.

### 7. **Docker**

**Installation Steps:**
1. **Install Docker:**
   ```bash
   sudo apt update
   sudo apt install -y apt-transport-https ca-certificates curl software-properties-common
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
   sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
   sudo apt update
   sudo apt install -y docker-ce
   ```

2. **Start Docker Service:**
   ```bash
   sudo systemctl start docker
   sudo systemctl enable docker
   ```

3. **Verify Installation:**
   ```bash
   docker --version
   ```

**Main Files:**
- **Dockerfile:** Yeh file Docker image ko build karne ke liye instructions deti hai.
- **docker-compose.yml:** Yeh file multiple Docker containers ko define aur manage karti hai.

**Example Dockerfile:**
   ```dockerfile
   FROM ubuntu:20.04
   RUN apt-get update && apt-get install -y nginx
   COPY . /usr/share/nginx/html
   CMD ["nginx", "-g", "daemon off;"]
   ```

**Example `docker-compose.yml`:**
   ```yaml
   version: '3'
   services:
     web:
       image: nginx
       ports:
         - "80:80"
   ```
__________________________________________________________________________________________________________________________________________________________________________________________________________

Basic example of an import file and configuration setup for managing and operating all the tools mentioned. This file will include configurations for Ansible, Jenkins, Kubernetes, Terraform, Chef, Nagios, and Docker.

### Example `setup.sh` Script

This script will help automate the setup process for all the tools. You'll need to run this script with `sudo` privileges on an Ubuntu machine.

```bash
#!/bin/bash

# Update and Upgrade System
echo "Updating and upgrading the system..."
sudo apt update && sudo apt upgrade -y

# Install Docker
echo "Installing Docker..."
sudo apt install -y docker.io
sudo systemctl start docker
sudo systemctl enable docker

# Install Ansible
echo "Installing Ansible..."
sudo apt install -y ansible

# Install Jenkins
echo "Installing Jenkins..."
sudo apt install -y openjdk-11-jdk
wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
echo "deb http://pkg.jenkins.io/debian-stable binary/" | sudo tee /etc/apt/sources.list.d/jenkins.list
sudo apt update
sudo apt install -y jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins

# Install Kubernetes
echo "Installing Kubernetes..."
sudo apt install -y apt-transport-https ca-certificates curl
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
echo "deb http://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
sudo apt update
sudo apt install -y kubelet kubeadm kubectl

# Initialize Kubernetes Cluster
echo "Initializing Kubernetes cluster..."
sudo kubeadm init

# Set Up Local kubeconfig
echo "Setting up kubeconfig..."
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config

# Install Flannel Network Plugin
echo "Installing Flannel network plugin..."
kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml

# Install Terraform
echo "Installing Terraform..."
wget https://releases.hashicorp.com/terraform/1.5.5/terraform_1.5.5_linux_amd64.zip
unzip terraform_1.5.5_linux_amd64.zip
sudo mv terraform /usr/local/bin/
rm terraform_1.5.5_linux_amd64.zip

# Install Chef Workstation
echo "Installing Chef Workstation..."
wget https://packages.chef.io/files/stable/chef-workstation/23.6.10/debian/11/chef-workstation_23.6.10-1_amd64.deb
sudo dpkg -i chef-workstation_23.6.10-1_amd64.deb

# Install Nagios
echo "Installing Nagios..."
sudo apt install -y wget build-essential libgd-dev libapache2-mod-php php-gd
wget https://github.com/NagiosEnterprises/nagioscore/archive/refs/tags/4.4.6.tar.gz
tar xzf 4.4.6.tar.gz
cd nagioscore-4.4.6
./configure
make all
sudo make install
sudo make install-init
sudo make install-commandmode
sudo make install-config
sudo make install-webconf

# Create Nagios Admin User
echo "Creating Nagios admin user..."
sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin

# Start Nagios
echo "Starting Nagios..."
sudo systemctl start nagios
sudo systemctl enable nagios

# Print End Message
echo "All tools installed and configured successfully!"
```

### Notes:
1. **Permissions**: Ensure you have sudo privileges to execute the script.
2. **Dependencies**: The script installs dependencies required for each tool.
3. **Verification**: After running the script, verify each tool's installation by checking their respective version commands (e.g., `docker --version`, `ansible --version`, etc.).
4. **Custom Configurations**: Depending on your use case, you might need to add additional configurations or setup files specific to each tool.

You can save this script as `setup.sh`, make it executable (`chmod +x setup.sh`), and run it using `sudo ./setup.sh`. This script will help streamline the installation process for all the mentioned tools.
