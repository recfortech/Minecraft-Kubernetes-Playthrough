[Failed to log in invalid session fix](https://github.com/itzg/docker-minecraft-server/discussions/1228)
>
>
>
Failed to log in invalid session try restarting your game and the launcher #1228
Answered by taeraeyttaejae
>
barseghyanartur asked this question in Q&A:
>
>
> I have the Minecraft server running using this docker-compose.yml:
> 
> ```yaml
> version: "3"
> 
> services:
>   mc:
>     image: itzg/minecraft-server
>     ports:
>       - 25565:25565
>     environment:
>       EULA: "TRUE"
>       DEBUG: "TRUE"
>     tty: true
>     stdin_open: true
>     restart: unless-stopped
> ```
> 
> Minecraft server version is 1.18.1.
> 
> I'm using the TLauncher (for Linux) version 1.18.1.
> 
> I can add the server in the list of servers. It reports OK. However, I can't connect to the server due to the following error:
> 
> ```
> Failed to connect to the server.
> Failed to log in: Invalid session (Try restarting your game and the launcher).
> ```
> 
> I do restart the game and the launcher, but the error persists. Any tips? Thanks in advance!
>
>

>
>taeraeyttaejae on Jan 24, 2022
>You have to pass ONLINE_MODE: "FALSE" in your environment variables, put it below DEBUG for example.
