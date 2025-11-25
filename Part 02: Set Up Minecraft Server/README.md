# Run Local Minecraft Server
<img width="1170" height="500" alt="image" src="https://github.com/user-attachments/assets/eb883af5-a0fd-4251-9e73-163f888f5fd3" />


## Pull image from DockerHub
Minecraft Server Image
[View on Docker Hub](https://hub.docker.com/r/recfortech/minecraft-world)

---
Open VSC in project directory

Start Minikube and open a local Kubernetes cluster:
```
minikube start --driver=docker
```
Verify the installation:
```
minikube status
```
---
## Deploy the Application

YAML files:
---
Deployment YAML:
```
containers:
      - name: minecraft-server
        image: recfortech/minecraft-world:latest
        ports:
        - containerPort: 25565
        env: 
        - name: EULA
          value: "true"
        - name: ONLINE_MODE
          value: "false"
```
Service YAML:


- Run ```port-forward``` command in separate window.
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
