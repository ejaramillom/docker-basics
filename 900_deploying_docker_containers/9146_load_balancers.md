# load balancers:

- EC2 manages the load balancers
- the load balancer is starting and stopping the containers (services)
- on `target groups` we have to edit the target group and the `health check path`
- on the HTTP URL we have to put `/goals` so that the load balancer work correctly

# security group

- we also have to add the `goals-app` security group is added
- we check the security group that is new, not the default one
- then we can copy the DNS name exposed in the resource group of AWS