# docker compose for utilities

in docker-compose.yaml

```
version: "3.8"
services:
  npm:
    build: ./
    stdin_open: true
    tty: true
    volumes:
    - ./:/app

```

- and then `docker-compose run --rm npm init` # run allows us to start a single service with its name, in this case `npm`
- 