# create images and start containers

- `docker container prune`
- `docker image prune -a`
- `docker-compose up` # it creates all images and starts all containers in attached mode
- `docker compose -d` # to start in detached mode
- `docker compose down -v` # deletes volumes and data