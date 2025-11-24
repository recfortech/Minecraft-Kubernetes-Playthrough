# Grafana Docker Image
## Run Grafana Image
Start the Docker container by binding Grafana to external port 3000.

Default admin user credentials are admin/admin.
```
docker run -d --name=grafana -p 3000:3000 grafana/grafana
```
> Further documentation on how to run Docker can be found at http://docs.grafana.org/installation/docker/⁠
> 
## Run Grafana within Newtork
Docker CLI to launch Prometheus container within the Minecraft network:
```
docker run -d --name grafana --network minecraft --network-alias grafana -p 3000:3000 grafana/grafana
```
