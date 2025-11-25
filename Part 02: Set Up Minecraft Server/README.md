# Run Local Minecraft Server
### Minecraft Server Image
Documentation Page:

https://hub.docker.com/r/recfortech/minecraft-world

---
### 1. Run ```port-forward``` command in separate window.
The command will run constantly to maintain the connection.
```
kubectl port-forward service/minecraft-server 25565:25565
```
---
### 2. Open Minecraft Launcher
1. Open Minecraft and navigate to the Multiplayer menu.
2. Click Add Server.
3. Assign Server Name of choice.
4. Enter the Server Address as **localhost:25565**.
5. Click Done.
6. Join the server.

![minecraft host port](https://github.com/user-attachments/assets/cf8bf1d2-604d-4c65-a286-8e3841e28f1d)
