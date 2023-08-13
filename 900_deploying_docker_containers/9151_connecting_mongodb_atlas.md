# mongodb atlas to delegate db management

- create the cluster in mongodb atlas
- start a new revision of the service running in EC2
- create new revision
- leave every config as they currently are and delete the previous mongodb container
- delete the volume related resources `EFS`
- delete the security group for the database

# connect the container to a mongodb atlas container

- access the container instance in `EC2`
- `MONGODB_URL=Cluster0.ntrwp.mongodb.net`
- `MONGODB_NAME=something` this is the database name we created in mongodb atlas