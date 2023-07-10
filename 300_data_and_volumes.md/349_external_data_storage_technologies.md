# volumes

## anonymous volumes

- we don't know where the volumes are saved in the machine
- `docker volume ls` # list all volumes with names
- if we stop the container, the volume dissapears! because is anonymous

## named volumes

- allow you to survive the data when moving, changinr, removing containers
- `docker run -d -p 2999:80 --rm --name feedback-app -v feedback:/app/feedback feedback-node:volumes`
- named volumes are not eliminated
- anonymous volumes are recreated every time we run a container


# bind mounts

- are managed by the developer
- the developer knows what folder we are using on our local machine
- then the container has access to the latest changes in the code
- are great for persistent, editable source code or data
- they affect the container

- `docker run -d -p 2999:80 --rm --name feedback-app -v feedback:/app/feedback -v "/Users/teacher/development/teaching/udemy:/app" feedback-node:volumes`

- here the /Users/teacher... route is the absolute path for the volume


### removing anonymous volumes

- anonymous volumes are removed automatically, when a container is removed. This happens when you start / run a container with the `--rm` option.
- If you start a container without that option, the anonymous volume would NOT be removed, even if you remove the container (with docker rm ...).
- if you then re-create and re-run the container (i.e. you run docker run ... again), a new anonymous volume will be created. So even though the anonymous volume wasn't removed automatically, it'll also not be helpful because a different anonymous volume is attached the next time the container starts (i.e. you removed the old container and run a new one).
- Now you just start piling up a bunch of unused anonymous volumes - you can clear them via `docker volume rm VOL_NAME` or `docker volume prune`. To list them use `docker volume ls`