# deleting containers

- `docker rm thing_name` Error because the container is running
- `docker stop name_thing`
- `docker rm one_thing other_thing more_things` we can separate multiple docker containers names to remove at once

or as well

- `docker container prune` removes all stopped containers at once

# deleting images

- `docker rmi thing_name_98734`

we can remove images if they are not being used anymore by any container

- `docker image prune`  removes all unused images at once