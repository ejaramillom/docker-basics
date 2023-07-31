# networking containers in AWS ECS

- we then have to go and create a new `networking only` cluster for our backend container
- name the cluster `goals-app`
- `create VPC` and set defaults as they are for all containers in the cluster
- then `create` (a cluster is the surrounding network)
- then `view cluster`
- we have to add `tasks` and `services`, services are based on tasks
- `create new task definition`
- `FARGATE` based networking
- 