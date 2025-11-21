# Minecraft on Kubernetes Playthrough
### IBM SRE Academy Final Project

Program Test Subject: Minecraft Server

## Docker CLI Command: 
```
docker run -d --name [CONTAINER_NAME_OR_ID] -p 25565:25565 -v [FILE PATH]:/data -e EULA=TRUE -e ONLINE_MODE=FALSE itzg/minecraft-server:latest
```
### Environment Variables
> Must accept the End User License Agreement
> ```
> -e EULA=TRUE
> ```

>TLauncher issue fix: 'Failed to log in: Invalid session'
>```
> -e ONLINE_MODE=FALSE
>```
>
>
