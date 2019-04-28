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

`CMD ["param1", "param2"]`<br>
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

### run
Create and starts a Docker container from a Docker image.

`docker run <image>`

#### --detach

Create and start a Docker container a Docker image in the background, printing the Docker container ID.

#### --publish
Create and starts a Docker container from a Docker image, publishing a container's port(s) to the host.

`docker run -p <host>:<container> <image>`

By default no traffice coming into the localhost network is redirect to into the Docker container network. To redirect a request into a Docker container, an explicit PORT mapping must be set up.

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

### logs
Fetch all the logs that have been emitted from a Docker container.

`docker logs <container>`

## Docker Compose

### up
Create and starts instances of all Docker containers in a Compose configuration file.

`docker-compose up`

#### --build

Build images before creating and starting instances of all Docker containers in a Compose configuration file.

`docker-compose up --build`

### down

Stops all Docker containers created by `up`.

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
