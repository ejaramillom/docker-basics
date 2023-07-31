# do not use docker compose for deployment

- this is a great tool for local development, not for deployment
- the only way to guarantee that the containers run in the same machine is putting them in the same task in the cluster, but that does not guarantee they use the same network, so we have to be careful about it
- we have to change our code
- in the name of mongodb we have to change the connectio to mongodb:
- change `mongodb` to `${process.env.MONGODB_URL}` and put it in the env variables file with `MONGODB_URL=mongodb`
- then publish the image to docker hub (the image of the backend container)
- retag the published container in the local machine
- `docker tag goals-node academind/goals-node`
- `docker push academind/goals-node`