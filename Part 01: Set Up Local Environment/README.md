# Installation Guide: Windows Users 

Step 1: Install WSL2 to use Ubuntu as your Linux distribution. 
---
Open PowerShell as Administrator and run:
```
wsl --install
```
Restart your computer.

Enable ```systemd```  in WSL2

- In Ubuntu:
```
sudo nano /etc/wsl.conf
```
Add:
```
[boot]
systemd=true
```
- Back in PowerShell (Windows):
```
wsl --shutdown
```
Reopen Ubuntu.

---
Step 2: Install Docker Engine
---
- In Ubuntu:
```
sudo apt-get update
sudo apt-get install -y ca-certificates curl gnupg

sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg \
  | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
  https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo $UBUNTU_CODENAME) stable" \
  | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt-get update
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

sudo usermod -aG docker $USER
newgrp docker
sudo systemctl enable --now docker
docker version
```
Step 3: Install kubectl
---
- In Ubuntu:
```
sudo apt-get update
sudo apt-get install -y kubectl
kubectl version --client
```
Step 4: Install Minikube
---
- In Ubuntu:
```
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version
```
Step 5: Install Python and Ansible
---
- In Ubuntu:
```
sudo apt-get install -y python3 python3-pip python3-venv pipx
pipx ensurepath
pipx install --include-deps ansible
ansible --version
```
Step 6: Install Visual Studio Code
---

[Download Visual Studio Code](https://code.visualstudio.com/download) and install.

- Open Visual Studio Code Terminal.
- Open a Remote Window.
- Open WSL.
- Create a new folder in **Ubuntu**.
- Download all files in the [Instalation Folder](https://github.com/recfortech/Minecraft-Kubernetes-Playthrough/tree/76e05e13596c5b1d297fd4178526ada86d63120a/Part%2001%3A%20Set%20Up%20Local%20Environment/Installation%20Files) and save in the new directory.
- Open the terminal from the new directory.
---
Step 7: Starting Minikube
---
- In WSL Terminal
```
minikube start --driver=docker
kubectl get nodes
```
---
Step 8: Verification
---
Run the following commands to check that all tools are working properly:
```
python3 --version
pip3 --version
docker --version
minikube version
kubectl version --client
ansible --version
```
