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
| Login to a Registry |   log in to your Registry | ``` docker login ``` or ``` docker login localhost:8080 ``` |
| Logout from a registry |   log out from your Registry | ```docker logout``` or ```docker logout localhost:8080``` |
| Searching an image | By using this docker command you can search any image from your docker | ```search nginx ``` or ```docker search --filter stars=3 --no-trun nginx``` |
| Pulling an Image	|  can be used to download a specific image or set of images | ```docker image pull nginx``` or ```docker image pull eon01/nginx localhost:5000/myadmin/nginx``` |
| Pushing an image |  can be used to push a specific image or set of images | ```docker image push eon01/nginx``` or ```docker image push eon01/nginx localhost:5000/myadmin/nginx``` |

## 3. Running Comtainers
| Command | Meaning | Syntax |
| --- | --- | --- |
| create a container	| to create a container without running | ```docker container create -t -i eon01/infinite --name XYZ``` |
| run a container | to run a container | ``` docker container run -it --name XYZ -d eon01/infinite ``` |
| rename a container | Use this rename a container |```docker container rename XYZ infinity ```|
|removing a container | to remove container in the topic | ```docker container rm infinite``` |
| Update a container | to update container in the topic | ```docker container update --cpu-shares 512 -m 300M infinite``` |

## 4. Starting or Stopping the Container
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

## 5. Container Information
| Command | Meaning | Syntax |
| --- | --- | --- |
| Fetching information From Running Containers | We can fetch information from running container | ```docker ps``` or ```docker container ls``` |
| fetching about all container | fetching about every container | ```docker container ls -a``` or ```docker ps -a``` |
| container log | We can use this command to see the container log | ```docker logs infinite``` |
|‘tail -f’ Containers’ Logs | Container isn't running in the foreground, and if there isn't anything running in the foreground, Docker closes automatically | ```docker container logs infinite -f``` |
| Inspecting Containers | inspecting containers	| ```docker container inspect infinite``` or ```docker container inspect --format '' $(docker ps -q)```|
| Containers Events	| To obtain real-time events from the server, use docker events | ```docker system events infinite``` |
| Public Ports | finding a public port | ```docker container port infinite``` |
| Running Processes | displaying the running processes in the container	| ```docker container top infinite``` |
| Container Resource Usage | It displays a realtime resources usage statics for containers | ```docker container stats infinite``` |
| Inspecting changes to files or directories on a container’s filesystem | inspecting changes to files or directories on a container’s filesystem | ```docker container diff infinite``` |

## 6. Managing Images
| Command | Meaning | Syntax |
| --- | --- | --- |
| listing images |  listing images | ```docker image ls``` |
| Building images From the current directory's Dockerfile | building from the current directory’s dockerfile | ```docker build``` | 	
| Building images From a GIT remote repository |  Building images command Using a remote GIT repository | ```docker build github.com/creack/docker-firefox``` |
| tagging and building	| This tagging and building | ```docker build -t eon/infinite``` |
| Specifying the Build Context while creating a Dockerfile | This is use to Build an image from a Dockerfile	| ```docker build -f myDockerfile```|
| Creating a Dockerfile from a URL | It wil help to create a dockerfile with a specific URL | ```curl example.com/remote/Dockerfile | docker build -f -``` |  
| removing image |  to removing a7n image | ```docker image rm nginx``` |
| Using a File or the Normal Input Stream to Load a Tarred Repository | Use STDIN or a tar archive to load an image | ```docker image load < ubuntu.tar.gz``` or ```docker build -f myOtherDockerfile ``` |
| Image Saving to a Tar Archiveard Input Stream	| It is used Save one or more images to a tar archive | ```docker image save busybox > ubuntu.tar``` |
| Showing the History of an Image | This command will let know the history of the image inside the docker | ``` image history``` |
| Making an Image Out of a Container | This command will help you to take an image out of the container | ```docker container commit nginx``` |
| image tagging	| We can use this image tagging | ```docker image tag nginx demo01/nginx``` |
| pushing an image | We can push any image through this command | ```docker image push demo01/nginx``` |

## 7. Networking
| Command | Meaning | Syntax |
| --- | --- | --- |
| overlay network | This is used to establish a distributed network between many Docker daemon hosts | ```docker network create -d overlay MyOverlayNetwork``` |
| Bridge network | To establish container test1 to bridge demo-bridge, type docker network connect demo-bridge test1 | ```docker network create -d bridge MyBridgeNetwork``` |
| removing a network | to remove an overlay network | ```docker network rm MyOverlayNetwork``` |
| network listing	|  to listing the overlay networks | ```docker network ls``` |
| Getting Information About a Network | We can get information about an overlay network with the help of this command | ```docker network inspect MyOverlayNetwork``` |
| Connecting a Running Container to a Network | By using this command we can connect a container to network | ```docker network connect MyOverlayNetwork nginx``` |
| Connecting a Container to a Network When it Starts | When the container starts we can use this command to connect a container to network	| ```docker container run -it -d --network=MyOverlayNetwork nginx``` |
| Disconnecting a Container from a Network | We can use this disconnecting a container from network | ```docker network disconnect MyOverlayNetwork nginx``` |
| Exposing Ports | We can expose the empty ports using this command | ```EXPOSE <port_number>``` |

## 8. Cleaning Docker
| Command | Meaning | Syntax |
| --- | --- | --- |
| Command for Removing a Running Container | We can remove a running container by using this command | ```docker container rm nginx``` |
| Command for Removing a Container and its Volume	| We can use this command for removing the container and the things inside it | ```docker container rm -v nginx``` |
| Command for Removing all Exited Containers | We can use this command for removing all the exited containers | ```docker container rm $(docker container ls -a -f status=exited -q)``` |
| Command for Removing All Stopped Containers | We can remove all the stopped containers by using this command | ```docker container rm `docker container ls -a -q` ``` |
| Command for Removing a Docker Image | This command is used fr removing a docker image | ```docker image rm nginx``` |
| Command for Dangling Images	| We can dangle the images with this command | ```docker image rm $(docker image ls -f dangling=true -q)``` |
| Command for Removing all Images	| We can remove all the image in the docker by using this commands | ```docker image rm $(docker image ls -a -q)``` | 
| Commands for Delete all Untagged Images | We can delete all the untagged images with the use of this command | ```docker image rm -f $(docker image ls | grep "^<none>" | awk "{print $3}")``` |
| Command for Stopping & Removing all Containers | For stopping and removing all the container we can use this command | ```docker container stop $(docker container ls -a -q) && docker container rm $(docker container ls -a -q)``` |
| Command for Removing Dangling Volumes	| We can remove all the dangling volumes by using this command | ```docker volume rm $(docker volume ls -f dangling=true -q)``` |
| Command for removing all unneeded (containers, images, networks and volumes) | This command is use to remove the unnecessary thing | ```docker system prune -f``` | 
| Command for Clean all | We cam use this command for cleaning everything in the docker | ```docker system prune -a``` |
