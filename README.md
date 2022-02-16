# DockerForDevelopers

## What is Docker?

    "Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. The service has both free and premium tiers. The software that hosts the containers is called Docker Engine. It was first started in 2013 and is developed by Docker, Inc." -Wikipedia

## Tools Using

- Docker for Desktop [here](https://docker.com)
- MongoDB
- some example apps to use in the containers

### Common Commands

> all Commands listed in the Docs [here](https://docs.docker.com/engine/reference/commandline/docker/)

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

#### Terminololgy

- all terms in the Docker [Glossary](https://docs.docker.com/glossary/)

> Note: all definitions here are taken from the Docker Glossary site.

- Container

    A container is a runtime instance of a docker image.

    A Docker container consists of

        A Docker image
        An execution environment
        A standard set of instructions

    The concept is borrowed from shipping containers, which define a standard to ship goods globally. Docker defines a standard to ship software.

- Volumes

    A volume is a specially-designated directory within one or more containers that bypasses the Union File System. Volumes are designed to persist data, independent of the container’s life cycle. Docker therefore never automatically deletes volumes when you remove a container, nor will it “garbage collect” volumes that are no longer referenced by a container. Also known as: data volume

    There are three types of volumes: host, anonymous, and named:

        A host volume lives on the Docker host’s filesystem and can be accessed from within the container.

        A named volume is a volume which Docker manages where on disk the volume is created, but it is given a name.

        An anonymous volume is similar to a named volume, however, it can be difficult to refer to the same volume over time when it is an anonymous volume. Docker handles where the files are stored.


- Image

    Docker images are the basis of containers. An Image is an ordered collection of root filesystem changes and the corresponding execution parameters for use within a container runtime. An image typically contains a union of layered filesystems stacked on top of each other. An image does not have state and it never changes.

- Compose

    Compose is a tool for defining and running complex applications with Docker. With Compose, you define a multi-container application in a single file, then spin your application up in a single command which does everything that needs to be done to get it running.

    *Also known as : docker-compose

- Dockerfile

    > More info [here](https://docs.docker.com/engine/reference/builder/)

    A Dockerfile is a text document that contains all the commands you would normally execute manually in order to build a Docker image. Docker can build images automatically by reading the instructions from a Dockerfile.

- .dockerignore

    > More info [here](https://docs.docker.com/engine/reference/builder/#dockerignore-file)

    Before the docker CLI sends the context to the docker daemon, it looks for a file named `.dockerignore` in the root directory of the context. If this file exists, the CLI modifies the context to exclude files and directories that match patterns in it. This helps to avoid unnecessarily sending large or sensitive files and directories to the daemon and potentially adding them to images using `ADD` or `COPY`.

    The CLI interprets the .dockerignore file as a newline-separated list of patterns similar to the file globs of Unix shells. For the purposes of matching, the root of the context is considered to be both the working and the root directory. For example, the patterns /foo/bar and foo/bar both exclude a file or directory named bar in the foo subdirectory of PATH or in the root of the git repository located at URL. Neither excludes anything else.

    If a line in .dockerignore file starts with # in column 1, then this line is considered as a comment and is ignored before interpreted by the CLI.

    Here is an example .dockerignore file:

    ```sh
    # comment
    */temp*
    */*/temp*
    temp?
    ```



- Dockerfile

    Defines the contents and startup behavior of a single container