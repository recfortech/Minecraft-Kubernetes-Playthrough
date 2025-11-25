# Install cAdvisor
Deploy the cAdvisor YAML file:
```
kubectl apply -f cadvisor.yaml
```
---
Check that the pod is running in default namespace:
```
kubectl get pods -n defalut
```
---
Grant Prometheus Access via RBAC
```
kubectl apply -f prometheus-rbac-cluster.yaml
```
Verify the role binding:
```
kubectl get clusterrolebinding prometheus-pod-reader-binding-cluster
```
