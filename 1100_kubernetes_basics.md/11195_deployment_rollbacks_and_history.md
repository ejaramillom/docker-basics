# deployment rollback and history

- `kubectl rollout status deployment/first-app` this command tells you what is going on with your deployment
- `kubectl rollout undo deployment/first-app` this undoes the previous deployment that had a typo, and did not finish correctly (the pod never started)
- `kubectl get pods` shows a correct list now
- `kubectl rollout history deployment/first-app --revision=3` shows us the third revision so we can check what containers were used
- `kubectl rollout status deployment/first-app --to-revision=1` this is based on the original code, the first release

# deleting deployments

- `kubectl delete service first-app`
- `kubectl delete deployment/first-app`
