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
