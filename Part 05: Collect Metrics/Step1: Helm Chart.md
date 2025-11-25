## Prometheus Operator through Helm Chart
Set up Prometheus Monitoring on Kubernetes Cluster with Prometheus operator through Helm Chart.
Install prometheus-community Helm Chart

[Documentation](https://helm.sh)
##

#### Install Helm:

[Documentation](https://helm.sh/docs/intro/install/#from-apt-debianubuntu)
```
sudo apt-get install curl gpg apt-transport-https --yes curl -fsSL https://packages.buildkite.com/helm-linux/helm-debian/gpgkey | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null echo "deb [signed-by=/usr/share/keyrings/helm.gpg] https://packages.buildkite.com/helm-linux/helm-debian/any/ any main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
```
##
#### Get Repository
```
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts
helm repo update
```
![helm repo 1](https://github.com/user-attachments/assets/bbb73900-b3a2-4db7-9d15-cf3c30364432)
##
#### Install Helm Chart
Install:
```
helm install prometheus-server prometheus-community/prometheus
```

Add itzg repository:
```
helm repo add itzg https://itzg.github.io/minecraft-server-charts/
```
Then run ```helm search repo itzg``` to see the charts.

