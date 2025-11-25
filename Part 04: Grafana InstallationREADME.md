# Grafana Installation in Minikube
### Install in Terminal (Visual Studio Code)
Apply grafana.yaml file:
```
kubectl apply -f grafana.yaml
```
![apply grafana yaml](https://github.com/user-attachments/assets/82435c84-96d5-439e-807b-fd5f451d8701)

Check the pod status:
```
kubectl get pods -n monitoring
```
In a **new terminal** access the Prometheus UI:
```
minikube service grafana-service -n monitoring
```
![grafana get pods monitoring](https://github.com/user-attachments/assets/c7083cce-5d9b-4507-afa9-5cf6ba936bb7)

--- 
### Using Ansible to Deploy
Run: 
```
ansible-playbook -i inventory.ini infra_grafana.yaml
```
![grafana infra yaml](https://github.com/user-attachments/assets/edf84be3-b87a-49fd-95c7-7c948fea3b13)

---
### Login to Grafana

Login:  ```admin/admin```

Go to **Configuration > Data Sources**  to check Prometheus, and Dashboards to see the "Example Dashboard".

<img width="1398" height="818" alt="image" src="https://github.com/user-attachments/assets/d18d804b-1ea0-4471-bfd9-2835a973e331" />
