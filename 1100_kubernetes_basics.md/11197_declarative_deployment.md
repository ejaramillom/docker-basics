# declarative deployment

## create deployment.yaml file

### /deployment.yaml

```
apiVersion: apps/v1
kind: Deployment # there is only a set of values to use here
metadata:
  name: second-app-deployment
spec: 
  replicas: 1
  template: # equivalent to --image attached to the deployment (this is always a pod, we cannot define a 'kind' here)
    metadata:
      labels: 
        app: second-app
    spec:  # the spec for the template
      containers: # we can have multiple containers using dashes
        - name: second-node-js
          image: academind/kub-first-app:2 # the name we would have used with --image 
        - name: ...
          image: ...


```

then in the console:

- `kubectl apply -f=deployment.yaml` # this fails because we are missing labels and selectors

### selectors

```
apiVersion: apps/v1
kind: Deployment # there is only a set of values to use here
metadata:
  name: second-app-deployment
spec: 
  replicas: 1
  selector: 
    matchLabels:
      app: second-app
      tier: backend
  template: # equivalent to --image attached to the deployment (this is always a pod, we cannot define a 'kind' here)
    metadata:
      labels: 
        app: second-app
        tier: backend
    spec:  # the spec for the template
      containers: # we can have multiple containers using dashes
        - name: second-node-js
          image: academind/kub-first-app:2 # the name we would have used with --image 
        - name: ...
          image: ...


```