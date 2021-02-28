# docker-cmd
Helpful Docker commands

## Docker Commands

### WORKDIR
Create and set a default working directory within a Docker image file system.

`WORKDIR <path/to/workdir>`

### COPY
Copy files and directories from source to a Docker image file system.

`COPY <src> <dest>`

### RUN
Execute command(s) and creates a new Docker image file. `RUN` is often used to install dependencies.

`RUN <cmd>`

### CMD
Set default command that will be executed on running Docker container.

`CMD <cmd>`

## Docker CLI

### build
Build a Docker image from a Dockerfile.

`docker build .`

#### --tag
Build a Docker image from a Dockerfile tagging the Docker image.

`docker build -t <id/name:tag> .`

Naming convention of a Docker image tag.

`yourDockerId/projectName:version`<br>
`bdunlop/dockerized-react-app:latest`

When creating and starting a Docker container from a tagged Docker image, `:latest` is automatically appended when not specified.

`docker run bdunlop/dockerized-react-app`

### --file

Specify path to an alternate Dockerfile to use to build a Docker image. (Default is Dockerfile)

`docker build -f Dockerfile.dev`

### history

Show the history of an image including image layers.

### run
Create and starts a Docker container from a Docker image.

`docker run <image>`

#### --detach
Create and start a Docker container a Docker image in the background, printing the Docker container ID.

`docker run <image> -d`

#### --publish
Create and starts a Docker container from a Docker image, publishing a container's port(s) to the host.

`docker run -p <host>:<container> <image>`

By default no traffic coming into the localhost network is redirect to into the Docker container network. To redirect a request into a Docker container, an explicit PORT mapping must be set up.

#### -it (--interactive + --tty)

The `-it` instructs Docker to allocate a pseudo-TTY connected to the container’s `STDIN`; creating an interactive `bash` shell in the container.

`docker run -it <image>`

#### --volume
Sets a mapping from a folder or file in a Docker containter to a folder or file on the local machine.

*More information required*

`docker run -v /usr/app/node_modules -v $(pwd):/usr/app <image>`

### exec
Run a command in a running Docker container.

`docker exec <container> <command>`

#### -it (--interactive + --tty)

The `-it` instructs Docker to allocate a pseudo-TTY connected to the container’s `STDIN`; creating an interactive `bash` shell in a runnning container.

`docker exec -it <container> <cmd>`

##### sh

Start a shell session with the default shell installed in the Docker container.

`docker exec -it <container> /bin/sh`

### ps
List all running Docker containers.

`docker ps`

#### --all

List all Docker containers.

`docker ps -a`

### stop
Stop a running Docker container.

`docker stop <container>`

### kill
Kill a running Docker container.

`docker kill <container>`

Kill all running Docker containers.

`docker kill $(docker ps -q)`

### rm
Remove one or more Docker containers.

`docker rm <container>`

Remove all Docker containers.

`docker rm $(docker ps -a -q)`

### image rm
Remove one or more Docker images.

`docker image rm <image>`

Remove all Docker images.

`docker rmi $(docker images -q)`

### logs
Fetch all the logs that have been emitted from a Docker container.

`docker logs <container>`

## Docker Compose

### up
Builds, (re)create and starts instances of all Docker containers in a Compose configuration file.

`docker-compose up`

#### --detach

Create and start a Docker container a Docker image in the background, printing the Docker container ID.

`docker-compose up -d`

#### --detach

Build Docker images before starting Docker container.

`docker-compose up --build`

### down

Stops and removes all Docker containers created by `up`.

`docker-compose down`

### ps

List all running Docker containers that belong to the Compose configuration file. 

Must be run from directory with Compose configuration file.

`docker ps`

#### --all

List all running Docker containers that belong to the Compose configuration file.

`docker ps -a`

###

## Files

### .dockerignore 
Exclude files and directories from a Docker image file system by adding a `.dockerignore` file to the root directory.
