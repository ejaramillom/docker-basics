# network for communicating containers

- `docker network create goals-net`
- `docker run --name mongodb --rm -d --network goals-network mongo`
- `docker run --name goals-backend --rm -d --network goals-network goals-node`

then we rewrite the docker files

```
mongodb://mongodb:27017/course-goals
```

- `docker build -t mongodb .`

we need to rewrite `localhost` in the frontend as `goals-backend` and then we build the image and run the container

- `docker run --name goals-frontend --network goals-network --rm -d -p 3000:3000 goals-frontend` but we need to keep exposed and published the port

## the previous does not work because react works in the browser, not in the server

- react code is not run in the container
- using `goals-backend` does not work, so we go back and write `localhost` everywhere, again
- `docker run --name goals-frontend --rm -d -p 3000:3000 goals-frontend` it does not care about the network
- `docker stop goals-backend`
- `docker run --name goals-backend -p 80:80 --rm -d --network goals-network goals-node` so that the port expose and publish to communicate with the frontend

we added the network so that the containers can communicate with each other

