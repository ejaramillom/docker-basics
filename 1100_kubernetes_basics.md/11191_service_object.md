# kubectl expose

- `kubectl expose deployment first-app --type=LoadBalancer --port=8080` # this create a service object in certain port
- ClusterIP is the default for the kubectl, but we can use other different typse such as NodePort, which means this deployment will be exposed with the help of the IP address of the running worker
- type LoadBalancer uses a load balancer on the infrastructure we are connected to, such as AWS, and it handles the requests to a single IP address. It is only available if the infrastructure service supports it

## list services
- `kubectl get services` # this lists a load balancer for first-app and a cluster ip for kubernetes
- `minikube service first-app` 

