# start container

- starts a previously built image container instance `docker start the_name`

with `docker run` the process is stuck in the terminal, it is attached

- `docker run -p 8000:80 2ddfheiueuh59jr`

## detached mode

- `docker run -p 8000:80 -d 2oiusdf98uih49`

the `-d` flag indicates that the process is detached from the terminal. 

## re-attach container

we can attach it again:

- `docker container attach 2oiusdf98uih49`

## logs

- `docker logs thing_name` will show the logs we have in the app from the console after attaching a container
- the standard for docker start is in detached mode

## attaching to already running containers

By default, if you run a Container without -d, you run in "attached mode".

If you started a container in detached mode (i.e. with -d), you can still attach to it afterwards without restarting the Container with the following command:

- `docker attach CONTAINER`

attaches you to a running Container with an ID or name of CONTAINER.