# how to update code in the containers and then in the pods

- `docker build -t academind/kub-first-app:2` with a number tag for the version
- `kubectl get deployments`
- `docker push academind/kub-first-app:2`
- `kubectl set image deployment/first-app kub-first-app=academind/first-app:2` first-app is the name of the deployment, it can change for us

## note

this name: `kub-first-app=academind/first-app` works as follows

kub-first-app is the name of the container we are running in the deployment, we can go in the minikube deployments monitor to check the name of the container that is running in the pod

then we copy the name of the image we just redeployed to docker hub, and assign it to the running container

- `kubectl rollout status deployment/first-app`