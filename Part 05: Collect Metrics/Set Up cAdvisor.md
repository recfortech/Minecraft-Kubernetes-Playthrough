## Setting up cAdvisor

Integrate cAdvisor with Prometheus to collect container-level metrics and display them in Grafana.
##
Check current number of metrics in Prometheus before and after installation to verify. 
- Prometheus Dashboard > Enter ```count({__name__=~".+"})``` > Execute

  
## Step 1: Running cAdvisor

Deploy cAdvisor using the provided YAML file:
```
kubectl apply -f cadvisor.yaml
```
Verify that the pod is running in the **default** namespace:
```
kubectl get pods -n default
```
## Step 2: Grant Prometheus Access via RBAC

This allows Prometheus cluster-wide read permisisons on pods and endpoints, so it can access metrics from any namespace. 

Apply the provided ClusterRole and ClusterRoleBinding configuration:
```
kubectl apply -f prometheus-rbac-cluster.yaml
```

Verify the role binding was created:
```
kubectl get clusterrolebinding prometheus-pod-reader-binding-cluster
```
<img width="916" height="105" alt="image" src="https://github.com/user-attachments/assets/f7b4a6c6-a37a-4df3-9e5a-a7970ca893cb" />

##
## Restart Deployments
Restart deployments to include cAdvisor.

Check deployment names with ```kubectl get deployment -n monitoring``` and restart.

Open dashboards again to verify update.

- ## Prometheus deployment:
Restart command:
```
kubectl rollout restart deployment prometheus-deployment -n monitoring
```

Dashboard:

<img width="1315" height="625" alt="image" src="https://github.com/user-attachments/assets/286c3d11-abf3-4247-99dd-fe821a991cfa" />


- ## Grafana deployment:
Restart command:
```
kubectl rollout restart deployment grafana-deployment -n monitoring
```

Dashboard:

<img width="1314" height="672" alt="image" src="https://github.com/user-attachments/assets/7c31b60e-340b-4ffe-a076-34c5cc1b2382" />

<img width="1318" height="582" alt="image" src="https://github.com/user-attachments/assets/51975223-6f71-4bed-82f4-6e7840123833" />


<img width="1317" height="674" alt="image" src="https://github.com/user-attachments/assets/573dad22-e27d-4680-8e06-69028f43dfd4" />

