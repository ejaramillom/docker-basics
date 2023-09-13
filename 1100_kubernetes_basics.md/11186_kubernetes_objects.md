# kubernetes objects

kubernetes work with objects:
- pods
- deployments
- services
- volumes

and so on. we can set them declaratively or imperatively.

## pods

- the smalles unit kubernetes interacts with
- pods hold containers, runs one or multiple containers
- tipically we have one container per pod
- has a cluster-internal IP by default, so they can communicate inside the cluster with other pods
- they communicate via localhost

### pods are ephemeral

- kubernetes start, stop and replace them as needed
- by default data is lost when a pod is deleted (similar to containers)

# controller

- manages a pod, so we have to create a 'controller'