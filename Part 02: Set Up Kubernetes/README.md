# Prometheus Installation in Kubernetes
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


