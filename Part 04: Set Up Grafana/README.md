# Grafana Installation in Minikube
### Install in Terminal (Visual Studio Code)
Apply grafana.yaml file:
```
kubectl apply -f grafana.yaml
```
Check the pod status:
```
kubectl get pods -n monitoring
```
In a **new terminal** access the Prometheus UI:
```
minikube service grafana -service -n monitoring
```
--- 
### Using Ansible to Deploy
Run: 
```
ansible-playbook -i inventory.ini infra_grafana.yaml
```
---
Login to Grafana
login ```admin/admin```
Go to **Configuration > Data Sources**  to check Prometheus, and Dashboards to see the "Example Dashboard".
