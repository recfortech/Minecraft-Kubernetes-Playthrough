### Chaos Engineering Test Case: *"EULA: "FALSE"*
#### Run on Docker Desktop
##
1. Run ```docker compose down``` to close current containter stack.

2.  Open ```docker compose.yaml``` and change the following value:
```
EULA: "FALSE"
```

Verify the Restart policy that should be set to:
```
# Restart policy
    restart: on-failure:5
```

3. Erase *"eula.txt"* from Minecraft server files on system
  
4. Run ```docker compose up```

##
## Results:

Server restarts several times but is unable to connect. 

<img width="1435" height="777" alt="image" src="https://github.com/user-attachments/assets/ed7a7f84-ba4f-4075-a11a-01ef57b84122" />
<img width="925" height="562" alt="image" src="https://github.com/user-attachments/assets/12400c88-2cee-4055-9811-c1c1ecd96307" />
