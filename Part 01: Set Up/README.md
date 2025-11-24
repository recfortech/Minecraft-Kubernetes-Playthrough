# Minecraft on Kubernetes Playthrough: Set Up
---
## Step #1: Minecraft Server Image
```
docker run -d --name minecraft-server -p 25565:25565 -v mc-data:/data recfortech/minecraft-world
```

#### Environment Variables
1. Must accept the End User License Agreement
```
-e EULA=TRUE
```

2. TLauncher issue fix: 'Failed to log in: Invalid session'
```
-e ONLINE_MODE=FALSE
```
---
## Step : Grafana
Grafana Docker image
Run the Grafana Docker container
Start the Docker container by binding Grafana to external port 3000.

Default admin user credentials are admin/admin.
```
docker run -d --name=grafana -p 3000:3000 grafana/grafana
```
> Further documentation on how to run Docker can be found at http://docs.grafana.org/installation/docker/⁠
