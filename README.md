# Docker-Commands
Basic commands for docker

To check container logs in docker,

docker logs nginx

sudo docker logs ebebb5c7ae0d

Container Restart :

docker container restart 1cc28748bd9d

All container restart :

docker-compose restart

To bash container:

docker exec -it ed7931b6b042 bash


Link: https://docs.docker.com/engine/reference/commandline/restart/
___________________________________________________________________________________________________________

To clear the volumes ---> docker volume prune

To list all the images present ---> docker images -a

To list the all the containers running ---> docker ps -a

To delete the all the images ---> docker rmi $(docker images -a)

To delete all the container while running ---> docker rm -f $(docker ps -a)

docker-compose up -d -----> To run the docker-compose file by pulling the docker images and create the containers.

docker-compose down -----> To stop the running containers of the certain directory.

docker rmi $(docker images -a) -----> To delete all the images that are created.

docker rmi <Image Id> -----> To delete the image. It will fail if it is running.

docker rmi -f <Image Id> -----> To force delete the image even in it is running in multiple repositories.

docker-compose down --volumes -----> To clear all volumes(logins, password) in the container.

docker images -----> To see all the images that are created.

docker ps -----> To see the all the running containers.

docker-compose logs -----> To see the logs of the containers.

docker exec -it <container name> /bin/bash -----> To connect to a container that is already running and access the files and folders.

docker rm <Container Id> -----> To remove the stopped container.

docker rm -f <Container Id> -----> To force remove the running container.

cat <File name with extension> -----> To view or open the file.

nano <File name with extension> -----> To edit the file.

rm <File name> -----> To delete a file.

docker-compose restart -----> To restart all the containers in the directory.

sudo chmod 666 /var/run/docker.sock -----> To enable permission to connect docker daemon.

docker logs [OPTIONS] CONTAINER ID - To get specific container log
_________________________________________________________________________________

To  pull docker image :

docker pull gcr.io/boldbi-dev-296107/bold-ums:6.3.3_dev
docker pull gcr.io/boldbi-dev-296107/bold-identity-api:6.3.3_dev
docker pull gcr.io/boldbi-dev-296107/bold-identity:6.3.3_dev

Then commit to 

IDP (Commit the local image to GCR)
 
docker tag gcr.io/boldbi-dev-296107/bold-identity:6.3.3_dev  gcr.io/boldreports-dev/bold-identity:5.1.20_05052023_predictor
docker tag gcr.io/boldbi-dev-296107/bold-identity-api:6.3.3_dev gcr.io/boldreports-dev/bold-idp-api:5.1.20_05052023_predictor
docker tag gcr.io/boldbi-dev-296107/bold-ums:6.3.3_dev gcr.io/boldreports-dev/bold-ums:5.1.20_05052023_predictor

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
IDP  (PUSH IMG TO GCR )
 
docker push gcr.io/boldreports-dev/bold-identity:5.1.20_05052023_predictor
docker push gcr.io/boldreports-dev/bold-idp-api:5.1.20_05052023_predictor
docker push gcr.io/boldreports-dev/bold-ums:5.1.20_05052023_predictor 
_________________________________________________________________________________
