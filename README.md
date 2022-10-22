# Docker Cheatsheet for Beginners

## 1. Installation of Docker
| Command | Meaning	| Syntax |
| --- | --- | --- |
| For Windows |	This command helps you to install Docker on windows. | https://download.docker.com/win/stable/InstallDocker.msi |
| For Linux	| This command helps you to install Docker on Linux. | curl -sSL https://get.docker.com/|sh |
| For mac	| This command helps you to install Docker on mac os.	| https://download.docker.com/mac/stable/Docker.dmg |

## 2. Docker Registry and Repository
| Command | Meaning | Syntax |
| Login to a Registry | This command helps you log in to your Registry |``` docker login 
                                                                            docker login localhost:8080 ```|
Logout from a registry	This command helps you log out from your Registry.	
docker logout
docker logout localhost:8080
Searching an image	By using this docker command you can search any image from your docker.	
search nginx
docker search --filter stars=3 --no-trunc nginx
Pulling an Image	This command can be used to download a specific image or set of images.	
docker image pull nginx
docker image pull eon01/nginx localhost:5000/myadmin/nginx
Pushing an image	This command can be used to push a specific image or set of images.	
docker image push eon01/nginx
docker image push eon01/nginx localhost:5000/myadmin/nginx
