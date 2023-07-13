# networks

- when you have multiple containers, you don't want to copy IP addresses to make them communicate
- we run `docker run --network my_network` so we don't have to manually communicate containers

## container networks

- `docker run -d --name mongodb --network favorites-net mongo`
- anyway, we need to create the network first

## creating networks

- `docker network create favorites-net`
- this is a docker internal network to make containers talk to each other
- now when we run the container of mongo, it makes part of the network
- we have to change the ports in the code: `mongodb://mongodb:27017/swfavorites` means that we just put the name of the container we want to communicate with

## ports

- they are only exposed in the `run` command when we want to communicate outside the docker networks, for instance, with the local machine

## docker IP resolving

- it detects outgoing requests and resolves the IP for the request