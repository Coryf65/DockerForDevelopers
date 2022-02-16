# DockerForDevelopers

## What is Docker?

    "Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. The service has both free and premium tiers. The software that hosts the containers is called Docker Engine. It was first started in 2013 and is developed by Docker, Inc." -Wikipedia

## Tools Needed

- Docker for Desktop [here](https://docker.com)
- MongoDB

## Terminololgy

- Container

- Volumes

- Image

- Networking

- Compose

- Dockerfile

- .dockerignore

### Common Commands

- More Commands in the Docs [here](https://docs.docker.com/engine/reference/commandline/docker/)

1. Build a image based off our `Dockerfile`

    ```sh
    docker build -t nameofcontainer .
    ```

2. See what images are built

    ```sh
    docker images
    ```

3. Run the image and build a conatiner

    ```sh
    # docker run -p port:port nameofimage
    docker run -p 4000:4000 name
    ```

4. See what containers are built

    ```sh
    docker ps
    ```

4. add this image to docker hub or get latest

    ```sh
    docker push
    docker pull
    ```