## kubectl

#### Get pods' names

```
kubectl get pods --no-headers -o custom-columns=":metadata.name"
```

#### Run interactive shell in a pod and remove a pod after exit

```
kubectl run  -it ubuntu --image=ubuntu:kinetic --restart=Never --rm -- /bin/bash
```
