# Docker useful commands

``` bash
## create image from docker file
sudo docker image build -t sample-spring-app .

## create container from image
sudo docker container run -it --publish 8080:8080 <image-id>

## go into container
docker container exec -it {container_name/ID} bash

## List all images that are locally stored with the docker engine:
docker image ls

```


## Docker Commands for Container and Image Information

``` bash
# List running containers:
docker ps

# lists both running containers and ones that have stopped
docker ps -a


```