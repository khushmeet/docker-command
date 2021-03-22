# docker-command
`HELPFUL DOCKER COMMANDS`

docker ps  list running containers. 
docker ps -a list all container including stopped container
docker pull  download a image from Docker Hub registry. Link to the docker image is always shown on the right at dockerhub.
docker build  is used to build your own container based on a Dockerfile. Common use is docker build . to build a container based on the Dockerfile in the current directory (the dot). docker build -t "myimage:latest" . creates a container and stores the image under the given name
docker images or docker image ls shows all local storage images
docker run  Run a docker container based on an image, i. e. docker run myimage -it bash. If no local image can be found docker run automatically tries to download the image from Docker hub.
docker logs display the logs of a container, you specified. To continue showing log updates just use docker logs -f mycontainer
docker volume ls  lists the volumes, which are commonly used for persisting data of Docker containers.
docker network ls - list all networks available for docker container
docker network connect adds the container to the given container network. That enables container communication by simple container name instead of IP.
docker rm   removes one or more containers. docker rm mycontainer, but make sure the container is not running
docker rmi  removes one or more images. docker rmi myimage, but make sure no running container is based on that image
docker stop   stops one or more containers. docker stop mycontainer stops one container, while docker stop $(docker ps -a -q) stops all running containers. 
docker start - starts a stopped container using the last state
docker update --restart=no updates container policies, that is especially helpful when your container is stuck in a crash loop
docker cp to copy files from a running container to the host or the way around. docker cp :/etc/file . to copy /etc/file to your current directory.
