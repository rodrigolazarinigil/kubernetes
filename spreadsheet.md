## Pod

### Config

Check current config
```
kubectl config view
```

Set a default namespace
```
kubectl config set-context --current --namespace=dataplatform
```

Port forward a service by an app label
```
kubectl port-forward $(kubectl get pod --selector="app=datalake-api" --output jsonpath='{.items[0].metadata.name}') 8000:8000
```

### List

Get a pod yaml
```
kubectl get pod <podname> -o yaml
```

List all pods (and keep watching)
```
kubectl get pods -w
```

Get all pods with "Completed" status
```
kubectl get pod --field-selector=status.phase==Succeeded
```

Get all pods with "Error" status
```
kubectl get pod --field-selector=status.phase==Failed
```

### Logs

Show logs of a pod
```
kubectl logs -f <podname>
```

### Delete

Delete a pod
```
kubectl get pod <podname>
```

Delete all pods with "Completed" status
```
kubectl delete pod --field-selector=status.phase==Succeeded
```

Delete all pods with "Error" status
```
kubectl delete pod --field-selector=status.phase==Failed
```
