
- build image from dockerfile `docker build .`

- list images from dockerfile `docker images`

- build image with tags `docker build -t localbuild:removeme .`

- renanme tag  `docker tag localbuild:removeme adtamayop/removeme`

- Login in `docker hub docker login`

- Push image to docker registry `docker push alfredodeza/removeme`

- Run container that emulates terminal `docker run -ti -d --name centos-test --rm centos:8 /bin/bash`

It uses -ti to allocate a TTY (emulates a terminal) and attaches stdin to it to interact with it in the terminal later. Next, the -d flag makes the container run in the background to prevent taking control of the current terminal. I assign a name (centos-test) and then use --rm so that Docker removes this container after stopping it. After issuing the command, a digest returns, indicating that the container has started. Now, verify it is running:

**Entrypoint**

Some containers get created with an ENTRYPOINT (and optionally a CMD) instruction. These instructions are meant to get the container up and running for a specific task. In the example container we just built for CentOS, the /bin/bash executable had to be specified because otherwise the container would not stay running. These instructions mean that if you want a long-running container, you should create it with at least an ENTRYPOINT that executes a program. Update the Dockerfile so that it looks like this:

    FROM centos:8
    RUN dnf install -y python38
    ENTRYPOINT ["/bin/bash"]

Now it is possible to run the container in the background without the need to specify the /bin/bash command:

    docker build -t localbuild:removeme .
    docker run --rm -it -d localbuild:removeme

- Acess to a running container `docker exec -it id_contenedor bash`

- Run linter over dockerfile `docker run --rm -i hadolint/hadolint < Dockerfile`



