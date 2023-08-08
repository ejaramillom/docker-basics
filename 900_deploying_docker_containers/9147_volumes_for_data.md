# persist data

- when a service is shut down, the data gets lost, particularly when speaking of db containers
- the solution is running a volume for the service in the cloud provider
- go to `task definition name`
- select the latest task
- then `create new revision`
- below we find the `volumes` section and then we pick a name and volume type `EFS` elastic file system
- we have to gpo to EFS system console to create a hard disk system
- on network access we have two mount targets, on the security groups we have to create a new group
- on the inbound groups we choose `NFS` and choose in the source the security group

## connecting with the mongodb container

- go to the container name
- set the mount point as `data/db` which is the same we used previously in docker compose
- then go to create new task definition
- platform version `1.4.0`
- then `force update task`

### remember the possible issue of rollback containers that try to access the db at the same time
