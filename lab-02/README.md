#### lab-02 : Dockerfile with custom env

Change directory to example two
```
cd module-01/example-02
```
Set Port
```
PORT=8080
```
Build Docker Image
```
docker build -t hello-world:v1.0.1 --build-arg PORT=$PORT .
```
Check Docker Image
```
docker images | grep hello-world
```
Run Docker Container from previously created image
```
docker run -p $PORT:$PORT hello-world:v1.0.1
```
Run Docker Container as background process
```
docker run -d -p $PORT:$PORT hello-world:v1.0.1
```
Check Docker Container
```
docker ps | grep hello-world
```
Access Application
```
curl http://localhost:$PORT
```

### Part-2 : Managin Docker Images
Access docker container
```
docker exec -it <container_name> <command>
```
Stops a running container
```
docker stop <container_name>
```
Starts a stopped container
```
docker start <container_name>
```
Restart a running container
```
docker restart <container_name>
```
Lists all running containers
```
docker ps
```
Lists all containers, including stopped ones
```
docker ps -a
```
Removes a stopped container
```
docker rm <container_name>
```
Forcefully removes a running container
```
docker rm -f <container_name>
```
Displays the logs of a container
```
docker logs <container_name>
```
Displays detailed information about a container
```
docker inspect <container_name>
```
Displays resource usage statistics for all running containers
```
docker stats
```
Renames a container
```
docker rename <old_container_name> <new_container_name>
```
Pauses a running container
```
docker pause <container_name>
```
Unpauses a paused container
```
docker unpause <container_name>
```
Displays the processes running in a container
```
docker top <container_name>
```
## Working With Docker Hub Registry
Docker Hub Login
```
docker login
```
Docker Hub Logout
```
docker logout
```
Push Local Image To Docker Hub

Tag image
```
docker tag <local-image> <docker-hub-username>/<repository-name>:<tag>
```
Push image
```
docker push <docker-hub-username>/<repository-name>:<tag>
```
Pull Docker Image From Docker Hub
```
docker pull <image-name>
```