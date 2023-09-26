# check if pods are running

in the `deployment.yaml`

```
spec:
  containers:
    - name: 
      image: 
      livenessProbe:
        httpGet:
          path: /
          port: 8080
          httpHeaders: ...
        periodSeconds: 10
        initialDelaySeconds: 5
```

this way, kubes will verify if the container is up and running