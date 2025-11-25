# Run Local Minecraft Server
<img width="514" height="147" alt="image" src="https://github.com/user-attachments/assets/e1389e82-8e25-4922-87ef-8fa4bf9d01c7" />


## Pull image from DockerHub
Minecraft Server Image: **recfortech/minecraft-world**

[View on Docker Hub](https://hub.docker.com/r/recfortech/minecraft-world)

---
Open VSC in project directory.

Start Minikube and open a local Kubernetes cluster:
```
minikube start --driver=docker
```
Verify the installation:
```
minikube status
```
---
## YAML files:

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
```
apiVersion: v1
kind: Service
metadata:
  name: minecraft-server
spec:
  selector:
    app: minecraft-server
  ports:
    - protocol: TCP 
      port: 25565
      targetPort: 25565
```
--- 
## Deploy the application
1. Apply the **deployment.yaml**
```
kubectl apply -f deployment.yaml
```
2. Verify the Pod status:

Creating the Pods may take a couple minutes.
```
kubectl get pods -a
```
3. Apply the **services.yaml**
```
kubectl apply -f services.yaml
```
4. Verify the Service:
```
kubectl get service
```
5. Port-Forward
---
- Run ```port-forward``` command in separate window.
The command will run constantly to maintain the connection.
```
kubectl port-forward service/minecraft-server 25565:25565
```
<img width="778" height="87" alt="image" src="https://github.com/user-attachments/assets/c6b27ed2-cf68-44f7-a63c-691990c1c4e1" />

---
## Open Minecraft Launcher
1. Open Minecraft and navigate to the Multiplayer menu.
2. Click Add Server.
3. Assign Server Name of choice.
4. Enter the Server Address as **localhost:25565**.
5. Click Done.
6. Join the server.

![minecraft host port](https://github.com/user-attachments/assets/cf8bf1d2-604d-4c65-a286-8e3841e28f1d)

---
## Check Kubernetes Dashboard
```
minikube dashboard
```

