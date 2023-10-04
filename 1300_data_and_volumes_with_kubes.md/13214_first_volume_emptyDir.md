# first time using kubes volumes

lets write the deployment.yaml and the service.yaml

```
apiVersion: apps/v1
kind: Deployment
metadata:
  name: kub-data-demo
spec: 
  replicas: 1
  selector: 
    matchLabels:
      app: story
      tier: backend
  template: 
    metadata:
      labels: 
        app: story
        tier: backend
    spec:  
      containers: 
        - name: story
          image: academind/kub-data-demo:1 
          volumeMounts: 
            - mountPath: /app/story
              name: story-volume
        - name: ...
          image: ...
      volumes:
        - name: story-volume
          emptyDir: {} # we don't have any specific configuration for this

```