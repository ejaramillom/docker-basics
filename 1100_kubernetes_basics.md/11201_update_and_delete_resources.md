# updating

- simply change the yaml file and then rerun the deployment/service and thats it

# deleting

- `kubectl delete -f=deployment.yaml,service.yaml`

this is not going to delete the deployment file, what is going to happen is that this command will delete all the resources associated with the deployment (containers, pods, images, workers, controller and so on)