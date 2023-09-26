# service.yml

```
apiVersion: v1
kind: Service
metadata:
  name: backend
spec: 
  selector:
    app: second-app # we copy here the selectors of the deployment
    tier: backend # we can ignore this key so that other pods with different tiers are selected by the same app: selector
  ports:
    - protocol: 'TCP'
      port: 80
      targetPort: 8080 # the port listening in the app
    - protocol: 'TCP'
      port: ...
      targetPort: ...
  type: ClusterIP (or NodePort or LoadBalancer the most common for world internet access)
```

this is a definition of the service resource

- then we run `kubectl apply -f service.yml`
- `minikube service backend`

this exposes the app and we can check the deployments and the service