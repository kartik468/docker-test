## Build a Docker image

To build a Docker image, run:

```
make build-docker-full
```

The resulting image will be tagged as grafana/grafana:dev.

**Note:** If you've already set up a local development environment, and you're running a `linux/amd64` machine, you can speed up building the Docker image:

1. Build the frontend: `go run build.go build-frontend`
1. Build the Docker image: `make build-docker-dev`

**Note:** If you are using Docker for macOS, be sure to set the memory limit to be larger than 2 GiB. Otherwise, `grunt build` may fail. The memory limit settings are available under **Docker Desktop** -> **Preferences** -> **Advanced**.


## run docker image

    sudo docker container run -it --publish 3000:3000 <image-id>