# deploying with AWS ECS

- clusters
- services
- task definitions
- container definitions
- then go on `configure` in AWS ECS custom containers
- name it `node-demo`
- in the `image` box `academind/node-example-1` if it is in dockerhub, otherwise we have to put the entire URL
- in the port mappings we have to put the ports we used to publish `port mappings`
- in `environment` we can put entrypoints and commands to run, as well as environment variables of the AWS console

## task definition

- this is the blueprint definition
- how the server should be configured
- this is a remote machine that could run one or more containers
- `FARGATE` compatibilities uses a serverless architecture, we can also select EC2 for a running instance virtual remote machine

## define your service

- here we can apply load balancers to manage the inbound requests

## configure clusters

- this is preety much as a network behavior for various containers
- in the task definitions, we can find an IP to visit our site
- `clusters > defaults > task: 45j4u5h-isdsd7-iausd3`