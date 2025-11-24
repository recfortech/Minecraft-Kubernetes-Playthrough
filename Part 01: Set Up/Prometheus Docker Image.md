# Prometheus Docker Image
## Run Prometheus Image File
Prometheus Docker container starts with a sample configuration that exposes it on port 9090.
```
docker run -p 9090:9090 prom/prometheus
```
> Further documentation on how to run Docker can be found at https://prometheus.io/docs/introduction/install/
## Run Prometheus within Newtork
Docker CLI to launch Prometheus container within the Minecraft network:
```
docker run -d --name prometheus --network minecraft --network-alias prometheus -p 9090:9090 prom/prometheus
```
