# Docker Cheatsheet for Beginners

## 1. Installation of Docker
| Command | Meaning	| Syntax |
| --- | --- | --- |
| For Windows |	 Docker on windows. | https://download.docker.com/win/stable/InstallDocker.msi |
| For Linux	|  Docker on Linux. | curl -sSL https://get.docker.com/ \| sh |
| For mac	|  Docker on mac os.	| https://download.docker.com/mac/stable/Docker.dmg |

## 2. Docker Registry and Repository
| Command | Meaning | Syntax |
| --- | --- | --- |
| Login to a Registry |   log in to your Registry | ``` docker login `````` docker login localhost:8080 ``` |
| Logout from a registry |   log out from your Registry | ```docker logout``` ```docker logout localhost:8080``` |
| Searching an image | By using this docker command you can search any image from your docker | ```search nginx ``` ```docker search --filter stars=3 --no-trun nginx``` |
| Pulling an Image	|  can be used to download a specific image or set of images | ```docker image pull nginx``````docker image pull eon01/nginx localhost:5000/myadmin/nginx``` |
| Pushing an image |  can be used to push a specific image or set of images | ```docker image push eon01/nginx``````docker image push eon01/nginx localhost:5000/myadmin/nginx``` |

## 3. Running Comtainers
| Command | Meaning | Syntax |
| --- | --- | --- |
| create a container	| to create a container without running | ```docker container create -t -i eon01/infinite --name XYZ``` |
| run a container | to run a container | ``` docker container run -it --name XYZ -d eon01/infinite ``` |
| rename a container | Use this rename a container |```docker container rename XYZ infinity ```|
|removing a container | to remove container in the topic | ```docker container rm infinite``` |
| Update a container | to update container in the topic | ```docker container update --cpu-shares 512 -m 300M infinite``` |

## 4. Commands for Starting or Stopping the Container
| Command | Meaning | Syntax |
| --- | --- | --- |
|starting a container | starting a container | ```docker container start nginx``` |
|stopping a container | stopping a container | ```docker container stop nginx``` |
|restarting the container	| restarting a container | ```docker container restart nginx``` |
|pausing the container | pausing a container | ```docker container pause nginx``` |
|unpausing the container | unpausing a container in the docker | ```docker container unpause nginx``` |
|Blocking a container | blocking a container in the docker | ```docker container wait nginx ``` |
| Sending a SIGKILL	| Sending a SIGKILL in the docker | ```docker container kill nginx``` |
|sending another signal | for sending another signal	| ```docker container kill -s HUP nginx``` |
|Connecting to an Existing Container | We can use this Connecting to an Existing Container	| ```docker container attach nginx``` |

## 5. Commands for Obtaining Container Information
| Command | Meaning | Syntax |
| --- | --- | --- |
| Fetching information From Running Containers | We can fetch information from running container | ```docker ps``` or ```docker container ls``` |
| fetching about all container | fetching about every container | ```docker container ls -a``` or ```docker ps -a``` |
| container log | We can use this command to see the container log | ```docker logs infinite``` |
|‘tail -f’ Containers’ Logs | Container isn't running in the foreground, and if there isn't anything running in the foreground, Docker closes automatically | ```docker container logs infinite -f``` |



 

This is the command use for inspecting containers	
docker container inspect infinite

docker container inspect --format '' $(docker ps -q)
Command for Containers Events	To obtain real-time events from the server, use docker events.	
docker system events infinite
Command for Public Ports	Use this command for finding a public port	
docker container port infinite
Command for Running Processes	We can use this commands for displaying the running processes in the container	
docker container top infinite
Command for Container Resource Usage	It displays a live stream of resources usage statics  for containers	
docker container stats infinite
Commands for Inspecting changes to files or directories on a container’s filesystem	This command is used for inspecting changes to files or directories on a container’s filesystem 	
docker container diff infinite