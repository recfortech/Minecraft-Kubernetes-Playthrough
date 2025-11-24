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
