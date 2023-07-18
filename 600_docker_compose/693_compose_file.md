# compose files

```
version: "3.8" # comes from docker hub compose files deployed
services:
  mongodb:
    image: 'mongo' # we don't need to detach or remove containers flags in docker compose
    volumes:
      - data:/data/db
    # environment:
      # MONGO_INITDB_ROOT_USERNAME: mongo
      # MONGO_INITDB_ROOT_PASSWORD: mongo
    # or we create a folder /env/mongo.env and then call the variables here
    env_file:
      - ./env/mongo.env
      
  backend:
    build: ./backend # so that it uses the dockerfile in the project folder
    # build: 
      # context: ./backend # path to the docker file and must include all the files that are copied to the container
      # dockerfile: Dockerfile
      # args:
        # some-arg: 1
    ports: 
      - '80:80'
    volumes:
      - logs:/app/logs
      - ./backend:/app # this is the bind mount using a relative path, not an absolute path
      - /app/node_modules
    env_file:
      - ./env/backend.env
    depends_on: # we tell docker compose to run the following services before running the backend
      - mongodb
    
  frontend:
    build: ./frontend
    ports: 
      - '3000:3000'
    volumes:
      - ./frontend/src:/app/src
    stdin_open: true
    tty: true # these two options are equivalent to `-it` flag in `docker run`
    depends_on:
      - backend

volumes: # for NAMED volumes we have to put an additional list in the level of indentation of services
  data:
  logs:

  networks: # we don't need to specify a network because docker compose puts all services in the same network
    goals-net:
      driver: bridge
  
```

we can use `mongodb` and `backend` names inside our code, despite the containers are named differently, like `docker-complete_mongo_1` and things like that