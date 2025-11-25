# Prometheus Installation in Kubernetes
### Install in Terminal (Visual Studio Code)
Make sure Minikube is running and using the docker driver before you continue.
```
minikube status
```
Upload YAML file to set up Prometheus:
```
kubectl apply -f prometheus.yaml
```
Check the pod status:
```
kubectl get pods -n monitoring
```
In a **new terminal** access the Prometheus UI:
```
minikube service prometheus-service -n monitoring
```
--- 
### Using Ansible to Deploy
Run: 
```
ansible-playbook -i inventory.ini infra.yaml
```
---
### Verify Prometheus Dashboard
Open the Prometheus dashboard and verify it's working by:

- Navigating to Status > Target Health (blue icon) to check the health of your targets.
- Query > **up**
- Query > **prometheus_build_info**

Expected output: pictures

---
### Upload Minecraft Server YAML files
With Minikube cluster already running, check status. Cluster should be empty.
```
kubectl get all
```

Upload Deployment YAML file.
```
kubectl apply -f deployment.yaml
```
Verify cluster and pod state.
```
kubectl get all
```
```
kubectl get pod
```
Upload Services YAML file.
```
kubectl apply -f services.yaml
```
Verify Service state.
```
kubectl get service
```



