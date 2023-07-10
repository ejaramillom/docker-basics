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