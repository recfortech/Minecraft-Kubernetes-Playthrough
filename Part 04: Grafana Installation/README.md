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
<img width="736" height="70" alt="image" src="https://github.com/user-attachments/assets/fcb06bd2-ccb0-4c3f-8da6-c1766782b47b" />

## 
In a **new terminal** access the Prometheus UI:
```
minikube service grafana-service -n monitoring
```
<img width="776" height="260" alt="image" src="https://github.com/user-attachments/assets/5816a47e-e11d-4427-9537-9d398f3a90b0" />


##
#### Using Ansible to Deploy
Run: 
```
ansible-playbook -i inventory.ini infra_grafana.yaml
```
![grafana infra yaml](https://github.com/user-attachments/assets/edf84be3-b87a-49fd-95c7-7c948fea3b13)

---
### Login to Grafana

Login:  ```admin/admin```

Go to **Configuration > Data Sources**  to check Prometheus, and Dashboards to see the "Example Dashboard".

<img width="1319" height="456" alt="image" src="https://github.com/user-attachments/assets/dd5226cf-7f96-450c-ac55-65f9cdee3f9b" />


<img width="1305" height="688" alt="image" src="https://github.com/user-attachments/assets/9a1a5489-2b10-4da7-a9af-c92f4a17ea62" />

