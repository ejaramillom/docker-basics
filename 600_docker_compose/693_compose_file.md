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
    image:

    
  frontend:
    image:

volumes: # for NAMED volumes we have to put an additional list in the level of indentation of services
  data:

  networks: # we don't need to specify a network because docker compose puts all services in the same network
    goals-net:
      driver: bridge
  
```