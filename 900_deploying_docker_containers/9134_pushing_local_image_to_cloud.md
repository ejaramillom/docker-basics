# option 1: deploy source code

- build image on remote machine
- push source code to remote machine, run docker build and then docker run
- this has unnecessary complexity and difficulty


# option 2: deploy the built image

- build image before deploying it
- just execute docker run in the virtual machine
- avoids unnecessary remote server work

## docker hub deployment

- create repository
- `node-example-1`
- create a docker ignore file with Dockerfile, node_modules and *.pem
- `docker build .` in a terminal not connected to the remote machine
- then we can push by renaming `docker tag node-example-1 academind/node-example-1`
- then on the list of images we should have the image we created with the new tag
- login to docker hub
- `docker login`
- and then push
- `docker push academind/node-example-1`