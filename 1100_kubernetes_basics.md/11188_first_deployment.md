# set up a first deployment

- `docker build -t kub-first-app .` # here we will build the image of the app
- `minikube status` # lets check if the pods are running
- `minikube start --driver=docker` # we create a virtual cluster for the pods using docker
- `kubectl help` # gives us all the info we need to work with
- `kubectl create deployment first-app --image=kub-first-app`

## this supposedly works, but does not, so if we check the deployments, they are not ready

- `kubectl get deployments` # we get the deployments list
- `kubectl get pods` # then an image pull error shows in the created pod

## the image specified in the image name is called inside a virtual machine (the iamge does not exist in the kubernetes cluster)

- we should specify images located in images located in image hubs (such as docker hub)

# enter in docker hub

- create new repository
- name it
- `docker tag kub-first-app academind/kub-first-app` # now the image exists in docker hub
- now we run the kubectl command again
- `kubectl create deployment first-app --image=kub-first-app`
- `kubectl get deployments` # we get one of one deployments list running
- `minikube dashboard`