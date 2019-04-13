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

`CMD ["param1", "param2"]`
`CMD <cmd>`

## Docker CLI

### build 
Build a Docker image from a Dockerfile tagging the Docker image.

`docker build -t <id/name:tag>`

Naming convention of a Docker image tag.

`yourDockerId/projectName:version`
`bdunlop/dockerized-react-app:latest`

### run
Create and starts a Docker container from a Docker image.

`docker run <image>`

### ps
List all running Docker containers.

`docker ps`

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

## Files

### .dockerignore 
Exclude files and directories from a Docker image file system by adding a `.dockerignore` file to the root directory.
