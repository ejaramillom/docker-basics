# what happens to restarting containers

- when a container restarts itself, the time kubectl takes to restart the container increases, and then increases the restart value, so that our deployment can aviod issues with wrongly set containers

# scaling

- with kubectl we can do:
- `kubectl scale deployment/first-app --replicas 3` so we are going to have 3 replicas, this starts three pods which become available for use
- for the case of our test app, when we crash our app in purpose, the other two pods are available, so the request gets redirected to the other pod

