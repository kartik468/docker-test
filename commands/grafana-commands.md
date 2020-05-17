## Build Grafana

Grafana consists of two components; the _frontend_, and the _backend_.

### Frontend

Before we can build the frontend assets, we need to install the dependencies:

```
yarn install --pure-lockfile
```

After the command has finished, we can start building our source code:

```
yarn start
```

Once `yarn start` has built the assets, it will continue to do so whenever any of the files change. This means you don't have to manually build the assets every time you change the code.

Next, we'll build the web server that will serve the frontend assets we just built.

### Backend

Build and run the backend by running `make run` in the root directory of the repository. This command compiles the Go source code and starts a web server.

> Are you having problems with [too many open files](#troubleshooting)?

By default, you can access the web server at `http://localhost:3000/`.

Log in using the default credentials:

| username | password |
| -------- | -------- |
| `admin`  | `admin`  |

When you log in for the first time, Grafana asks you to change your password.

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


## no space left issue when 'make run'

maybe your inotify resources exhausted, increase max_user_watches works for me.

$ cat /proc/sys/fs/inotify/max_user_watches # default is 8192 $ sudo sysctl fs.inotify.max_user_watches=1048576 # increase to 1048576

## How to fix docker: Got permission denied while trying to connect to the Docker daemon socket

https://docs.docker.com/engine/install/linux-postinstall/

https://www.digitalocean.com/community/questions/how-to-fix-docker-got-permission-denied-while-trying-to-connect-to-the-docker-daemon-socket