## kubectl

#### Get pods' names

```
kubectl get pods --no-headers -o custom-columns=":metadata.name"
```
