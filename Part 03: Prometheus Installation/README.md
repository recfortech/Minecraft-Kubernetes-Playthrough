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
![prometheus yaml](https://github.com/user-attachments/assets/5a33a701-4b13-409b-b3e4-f2fc94bb4e84)

Check the pod status:
```
kubectl get pods -n monitoring
```
<img width="654" height="57" alt="image" src="https://github.com/user-attachments/assets/800c44ff-8719-4264-87c7-4f91fd949e12" />

##
In a **new terminal** access the Prometheus UI:
```
minikube service prometheus-service -n monitoring
```
<img width="770" height="273" alt="image" src="https://github.com/user-attachments/assets/4fc8f378-4434-4c94-9c17-9726fb097183" />

##
#### Using Ansible to Deploy

Run: 
```
ansible-playbook -i inventory.ini infra.yaml
```
<img width="919" height="219" alt="image" src="https://github.com/user-attachments/assets/5bfd4821-e421-4227-ac21-e56a307f946c" />

##
### Verify Dashboard:

- ## Kubernetes Dashboard
```
minikube dashboard
```
- ## Prometheus Dashboard
Open the Prometheus dashboard and verify it's working by:

1. Navigating to Status > Target Health (blue icon) to check the health of your targets.
2. Query > **up**
3. Query > **prometheus_build_info**
  
![prometheus dashboard](https://github.com/user-attachments/assets/89250d32-1ed9-49cf-aa25-826cbab6cff4)

