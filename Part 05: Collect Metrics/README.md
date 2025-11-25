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
#### Install Chart
```
helm install prometheus-server prometheus-community/prometheus
```
##
#### Check Components:
```
kubectl get pods
```
<img width="887" height="175" alt="image" src="https://github.com/user-attachments/assets/b21de9e8-b9b1-46ab-8afa-68284e740e94" />

#### Expose as a node point:

  1. Check services:
```
kubectl get svc
```
<img width="897" height="175" alt="image" src="https://github.com/user-attachments/assets/98f689a1-bba1-4d7e-831c-b561ed34e5d2" />

##

  2. Expose service as NodePort:
<img width="915" height="51" alt="image" src="https://github.com/user-attachments/assets/6a8a47cc-7915-4cf1-a432-27f742c6b17e" />

##
  3. New NodePort created:
<img width="907" height="478" alt="image" src="https://github.com/user-attachments/assets/2676d032-4ddd-4e78-a648-9dd5a2ef5fe2" />

