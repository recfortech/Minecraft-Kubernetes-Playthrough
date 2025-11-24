## Step : Grafana
Grafana Docker image
Run the Grafana Docker container
Start the Docker container by binding Grafana to external port 3000.

Default admin user credentials are admin/admin.
```
docker run -d --name=grafana -p 3000:3000 grafana/grafana
```
> Further documentation on how to run Docker can be found at http://docs.grafana.org/installation/docker/⁠
