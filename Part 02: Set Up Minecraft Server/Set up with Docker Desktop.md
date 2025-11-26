# Run Local Minecraft Server on Docker Desktop
<img width="514" height="147" alt="image" src="https://github.com/user-attachments/assets/e1389e82-8e25-4922-87ef-8fa4bf9d01c7" />


### Minecraft Container Image
Minecraft Server Image name: **recfortech/minecraft-world**

[View on Docker Hub](https://hub.docker.com/r/recfortech/minecraft-world)

---
# Installation

## Option #1: Run Minecraft with Docker CLI command to create container:
```
docker run -d --name minecraft -p 25565:25565 -e EULA=true -v C:\some\path\on\my\pc:/data --restart on-failure recfortech/minecraft-world:latest
```

## Option #2: Run Minecraft with Docker Compose

1. Create ```docker-compose.yaml``` with Visual Studio Code.
2. Save file in local directory.
3. Run ```docker compose up -d``` including Prometheus and Grafana within that same directory.

```
# docker-compose.yaml file
services:
  minecraft:
    image: recfortech/minecraft-world
    tty: true
    stdin_open: true
    ports:
      - "25565:25565"
    environment:
      EULA: "TRUE"
      ONLINE_MODE: "FALSE"
    volumes:
      # Assign directory 'data' to the container's /data path
      - L:\Minecraft Docker Server\mc-data:/data
    # Restart policy
    restart: on-failure:5
    # The docker networks configuration for the minecraft service
    networks:
      # The name of the network to put the minecraft service into
      minecraft:
        # A network alias within the docker network to give the minecraft service
        aliases:
          - minecraft
  prometheus:
    image: prom/prometheus
    tty: true
    stdin_open: true
    ports:
      - "9090:9090"
    # Restart policy
    restart: on-failure:5
    networks:
      minecraft:
        aliases:
          - prometheus
  grafana:
    image: grafana/grafana
    stdin_open: true
    ports:
      - "3000:3000"
    # Restart policy
    restart: on-failure:5
    networks:
      minecraft:
        aliases:
          - grafana

# Docker network configurations
networks:
  # The network to configure
  minecraft:
    # The minecraft network will be created if it does not exist
    name: minecraft
```
##
### Create "Minecraft Network" in ```docker-compose```
- Prometheus server URL: ```http://prometheus:9090```

> Docker CLI:
```
docker run -d --name prometheus --network minecraft --network-alias prometheus -p 9090:9090 prom/prometheus
```
>

- Grafana server URL: http://grafana:3000
> Docker CLI
```
docker run -d --name grafana --network minecraft --network-alias grafana -p 3000:3000 grafana/grafana
```

##
### Open Minecraft Launcher
1. Open Minecraft and navigate to the Multiplayer menu.
2. Click Add Server.
3. Assign Server Name of choice.
4. Enter the Server Address as **localhost:25565**.
5. Click Done.
6. Join the server.

> Server Address will be the port mapped or bound the container to the PC
> localhost:25565
>
>Confirm the correct IP address 
> •	Local IP: On the server computer, open the command prompt and type ipconfig (Windows) or >ip a (Linux) to find the local IPv4 address. This is the address you should use to connect >from another computer on the same network.
> •	localhost: If connecting from the same computer that the server is running on, use >localhost or 127.0.0.1 as the server address. 

![minecraft host port](https://github.com/user-attachments/assets/cf8bf1d2-604d-4c65-a286-8e3841e28f1d)

<img width="924" height="563" alt="image" src="https://github.com/user-attachments/assets/a2aa0a8c-dda4-494b-813a-b3339c8220ca" />

