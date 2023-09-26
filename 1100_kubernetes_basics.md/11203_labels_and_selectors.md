# labels and selectors

```
matchExpressions:
  - {key: app, operator: NotIn, values: [second-app, first-app]}
```

this way we could use expression to select tiers and labels

# delete by label

add labels to deployment.yaml

```
metadata:
  name: Second-app-deployment
  labels:
    group: example
```

after applying the changes, we cand elete by label:

- `kubectl delete deployments,services -l group=example`

this deleted the deployment and the services for the labels