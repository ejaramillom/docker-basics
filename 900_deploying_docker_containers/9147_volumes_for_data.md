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