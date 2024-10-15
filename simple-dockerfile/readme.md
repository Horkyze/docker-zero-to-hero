# Rails Hello World Docker Container

This README provides instructions on how to build and run a Docker container for a Rails "Hello World" application.

## Prerequisites

- Docker installed on your machine. If you haven't installed Docker yet, please follow the official [Docker installation guide](https://docs.docker.com/get-docker/).

## Building the Docker Image

To build the Docker image, run the following command in the terminal from the directory containing the Dockerfile:

```bash
docker build -t rails-hello-world .
```

Let's break down this command:

- `docker build`: This is the command to build a Docker image.
- `-t rails-hello-world`: The `-t` flag tags the image with a name. In this case, we're naming it "rails-hello-world".
- `.`: The dot at the end specifies the build context, telling Docker to look for the Dockerfile in the current directory.

This command will create a Docker image based on the instructions in your Dockerfile.

## Running the Docker Container

After building the image, you can run the container using the following command:

```bash
docker run -p 3000:3000 rails-hello-world
```

Here's what each part of this command does:

- `docker run`: This command creates and starts a new container based on an image.
- `-p 3000:3000`: This flag maps port 3000 of the container to port 3000 on your host machine. The format is `-p host_port:container_port`.
- `rails-hello-world`: This is the name of the image we want to run.

After running this command, your Rails application should be accessible at `http://localhost:3000` in your web browser.

## Stopping the Container

To stop the running container, you can press `Ctrl+C` in the terminal where the container is running.

## Additional Docker Commands

- To see a list of running containers: `docker ps`
- To see a list of all containers (including stopped ones): `docker ps -a`
- To remove a container: `docker rm <container_id>`
- To see a list of all images: `docker images`
- To remove an image: `docker rmi <image_id>`

Happy coding with Docker!
