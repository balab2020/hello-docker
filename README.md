**Prerequisites:**
- [Install Docker for Windows](https://docs.docker.com/v17.09/docker-for-windows/install/)
- Make sure you use Linux Containers for this example
- I used Visual Studio Code as development IDE

**Build docker image**

`docker build -t balab2020/node-web-app .`

balab2020/node-web-app is docker image name

**Run Docker Image**

`docker run -p 49160:8080 -d balab2020/node-web-app`

-d runs the container in detached mode
-p flag redirects a public port to a private port inside the container

49160 is the system ip mapped with docker instance 8080 ip

**List running images**

`docker ps`

Sample Output:

| CONTAINER ID | IMAGE NAMES            | COMMAND     | CREATED        | STATUS        | PORTS                |
| ------------ | ---------------------- | ----------- | -------------- | ------------- | -------------------- |
| c249cfa8fd79 | balab2020/node-web-app | "npm start" | 35 seconds ago | Up 18 seconds | 0.0.0.0:49160->8080/ |

**Connect to docker instance**

`docker exec -it CONTAINER_ID bash`

**Display logs of container**

`docker logs CONTAINER_ID`

**Check running instance service**

`curl -i localhost:49160`
