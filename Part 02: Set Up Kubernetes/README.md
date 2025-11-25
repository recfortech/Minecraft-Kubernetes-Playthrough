# Prometheus Installation in Kubernetes
### Install in Terminal
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
### Verify Prometheus Dashboard
Open the Prometheus dashboard and verify it's working by:

- Navigating to Status > Target Health (blue icon) to check the health of your targets.
- Query > **up**
- Query > **prometheus_build_info**

Expected output: pictures


