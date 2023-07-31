# networking containers in AWS ECS

- we then have to go and create a new `networking only` cluster for our backend container
- name the cluster `goals-app`
- `create VPC` and set defaults as they are for all containers in the cluster
- then `create` (a cluster is the surrounding network)
- then `view cluster`
- we have to add `tasks` and `services`, services are based on tasks
- `create new task definition`
- `FARGATE` based networking
- then `add container`
- use the image name in docker hub `academind/goals-app`
- in `env` we want to change the starting of nodemon. Now we do not want to execute the code with nodemon.
- in commands, `node,app.js` without spaces, and then it will run that expression in the server
- then you want to add the env variables defined in the dockerfile

## database URL

- we set in AWS the `ENV` named `MONGODB_URL value localhost` not the URL we changed previously
- finally we click add to keep the container
