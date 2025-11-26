# Run Local Minecraft Server on Docker Desktop
<img width="514" height="147" alt="image" src="https://github.com/user-attachments/assets/e1389e82-8e25-4922-87ef-8fa4bf9d01c7" />


### Minecraft Container Image
Minecraft Server Image name: **recfortech/minecraft-world**

[View on Docker Hub](https://hub.docker.com/r/recfortech/minecraft-world)

---

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
