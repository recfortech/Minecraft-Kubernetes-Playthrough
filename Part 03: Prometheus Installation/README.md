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
<img width="767" height="296" alt="image" src="https://github.com/user-attachments/assets/ce287041-9c07-407d-a0e9-0a3bd2f9e3f7" />

--- 
### Using Ansible to Deploy
Run: 
```
ansible-playbook -i inventory.ini infra.yaml
```
![ansible deploy](https://github.com/user-attachments/assets/1385c654-7584-4aac-8c9d-6c04bdea9999)

---
### Verify Prometheus Dashboard
Open the Prometheus dashboard and verify it's working by:

- Navigating to Status > Target Health (blue icon) to check the health of your targets.
- Query > **up**
- Query > **prometheus_build_info**
![prometheus dashboard](https://github.com/user-attachments/assets/89250d32-1ed9-49cf-aa25-826cbab6cff4)




