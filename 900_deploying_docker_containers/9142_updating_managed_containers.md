# updating remote container

- to update the code in the remote container we rebuild the image locally
- `docker build -t node-dep-example-1 .`
- then retag the container
- `docker tag node-dep-example-1 academind/node-example-1`
- then push again the image to docker hub
- `docker push academind/node-example-1`

## on AWS

- her we have to go to `AWS clusters > default`
- go to `tasks`
- then go to `task definition` link on the list of tasks that are running, in this case the currently running task with the app that was deployed
- `create new revision`
- leave the settings that were already selected the first time
- then `actions`
- then `update service`
- `skip to review`
- `update service`
- then we wait for it to finish running the task, and then we search for the IP to connect

## load balancers for service networking

In AWS, a load balancer is a service that distributes incoming network traffic across multiple targets (e.g., Amazon EC2 instances, containers, IP addresses, Lambda functions) to ensure high availability and fault tolerance. It acts as a single point of contact for clients (e.g., web browsers) and forwards incoming requests to the available targets, which helps distribute the load evenly and prevent any single resource from being overwhelmed.

AWS provides different types of load balancers:

- Classic Load Balancer (CLB): This is the oldest type of load balancer in AWS and is suitable for traditional EC2 instances. It operates at Layer 4 (Transport Layer) and Layer 7 (Application Layer) of the OSI model.

- Application Load Balancer (ALB): This operates at Layer 7 and is designed for modern application architectures, including microservices and containers. It supports advanced routing and content-based routing based on HTTP/HTTPS requests.

- Network Load Balancer (NLB): This operates at Layer 4 and is ideal for handling high-throughput and low-latency traffic. It is often used for UDP, TCP, and TLS traffic.

To avoid searching for the IP address of services running in AWS ECS, you can make use of AWS Application Load Balancer (ALB) or Network Load Balancer (NLB) as the single point of contact for your services. When you deploy your services in AWS ECS, you can associate them with the ALB or NLB target group. The load balancer will handle the routing and distribution of incoming requests to the appropriate containers or EC2 instances.

The load balancer will have a DNS name, such as `my-load-balancer-1234567890.us-west-2.elb.amazonaws.com`. You can use this DNS name as the URL to access your services instead of searching for IP addresses. The DNS name is automatically managed by AWS, and it will always resolve to the correct IP addresses of the containers or EC2 instances behind the load balancer.

By using an ALB or NLB, you can have a reliable URL endpoint to access your services, and AWS will take care of handling the traffic distribution and failover for you. This provides a scalable and efficient solution for managing your applications in AWS ECS.