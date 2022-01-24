
- build image from dockerfile `docker build .`

- list images from dockerfile `docker images`

- build image with tags `docker build -t localbuild:removeme .`

- renanme tag  `docker tag localbuild:removeme adtamayop/removeme`

- Login in `docker hub docker login`

- Push image to docker registry `docker push alfredodeza/removeme`

- Run container that emulates terminal `docker run -ti -d --name centos-test --rm centos:8 /bin/bash`

It uses -ti to allocate a TTY (emulates a terminal) and attaches stdin to it to interact with it in the terminal later. Next, the -d flag makes the container run in the background to prevent taking control of the current terminal. I assign a name (centos-test) and then use --rm so that Docker removes this container after stopping it. After issuing the command, a digest returns, indicating that the container has started. Now, verify it is running:
