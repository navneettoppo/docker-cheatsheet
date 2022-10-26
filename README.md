# Docker Cheatsheet for Beginners

## 1. Installation of Docker
| Command | Meaning	| Syntax |
| --- | --- | --- |
| For Windows |	This command helps you to install Docker on windows. | https://download.docker.com/win/stable/InstallDocker.msi |
| For Linux	| This command helps you to install Docker on Linux. | curl -sSL https://get.docker.com/ \| sh |
| For mac	| This command helps you to install Docker on mac os.	| https://download.docker.com/mac/stable/Docker.dmg |

## 2. Docker Registry and Repository
| Command | Meaning | Syntax |
| --- | --- | --- |
| Login to a Registry | This command helps you log in to your Registry | ``` docker login `````` docker login localhost:8080 ``` |
| Logout from a registry | This command helps you log out from your Registry | ```docker logout``` ```docker logout localhost:8080``` |
| Searching an image | By using this docker command you can search any image from your docker | ```search nginx ``````docker search --filter stars=3 --no-trun nginx``` |
| Pulling an Image	| This command can be used to download a specific image or set of images | ```docker image pull nginx``````docker image pull eon01/nginx localhost:5000/myadmin/nginx``` |
| Pushing an image | This command can be used to push a specific image or set of images | ```docker image push eon01/nginx``````docker image push eon01/nginx localhost:5000/myadmin/nginx``` |

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