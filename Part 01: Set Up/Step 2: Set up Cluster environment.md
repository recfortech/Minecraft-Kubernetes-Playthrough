

Step 4 – Install kubectl (Official Repo)
sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg \
  https://pkgs.k8s.io/core:/stable:/v1.31/deb/Release.key

echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] \
  https://pkgs.k8s.io/core:/stable:/v1.31/deb/ /" \
  | sudo tee /etc/apt/sources.list.d/kubernetes.list

sudo apt-get update
sudo apt-get install -y kubectl
kubectl version --client

Step 5 – Install Minikube (Official Binary)
curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
sudo install minikube-linux-amd64 /usr/local/bin/minikube
minikube version

Step 6 – Install Python, pip, venv, pipx, and Ansible
sudo apt-get install -y python3 python3-pip python3-venv pipx
pipx ensurepath
pipx install --include-deps ansible
ansible --version


Step 7 - Install Prometheus: sudo apt install prometheus


Step 8 install helm
https://helm.sh/docs/intro/install/#from-apt-debianubuntu

 sudo apt-get install curl gpg apt-transport-https --yes
curl -fsSL https://packages.buildkite.com/helm-linux/helm-debian/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
echo "deb [signed-by=/usr/share/keyrings/helm.gpg] https://packages.buildkite.com/helm-linux/helm-debian/any/ any main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list


step 9 configure helm chart
https://gitlab.com/nanuchi/youtube-tutorial-series/-/blob/master/prometheus-exporter/install-prometheus-commands.md
command helm install prometheus prometheus-community/kube-prometheus-stack

view link chart:
install Prometheus-operator

add repos

helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo add stable https://charts.helm.sh/stable
helm repo update


install chart

helm install prometheus prometheus-community/kube-prometheus-stack

port forward grafana: kubectl port-forward deployment/prometheus-grafana 3000



---
Docker Hub: https://hub.docker.com/r/recfortech/minecraft-world

Docker CLI image pull
docker pull recfortech/minecraft-world:latest

docker run -d --name minecraft-server -p 25565:25565 -v mc-data:/data -e EULA=TRUE -e ONLINE_MODE=FALSE recfortech/minecraft-world
