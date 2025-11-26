## Setting up cAdvisor

Integrate cAdvisor with Prometheus to collect container-level metrics and display them in Grafana.
##
Check current number of metrics in Prometheus before and after installation to verify. 
- Prometheus Dashboard > Enter ```count({__name__=~".+"})``` > Execute
##
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

Restart Prometheus deployment:
```
kubectl get deployment -n monitoring
```
```
kubectl rollout restart deployment prometheus-deployment -n monitoring
```
