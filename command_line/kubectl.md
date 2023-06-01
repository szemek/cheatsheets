## kubectl

[kubectl cheatsheet](https://kubernetes.io/docs/reference/kubectl/cheatsheet/)

#### Get pods' names

```
kubectl get pods --no-headers -o custom-columns=":metadata.name"
```

#### Run interactive shell in a pod and remove a pod after exit

```
kubectl run  -it ubuntu --image=ubuntu:kinetic --restart=Never --rm -- /bin/bash
```

#### Get resources in a namespace

```
kubectl api-resources --verbs=list --namespaced -o name \
  | xargs -n 1 kubectl get --show-kind --ignore-not-found -n <namespace>
```

```
kubectl get all
```

Reference: https://www.studytonight.com/post/how-to-list-all-resources-in-a-kubernetes-namespace

#### Restart deployment

```
kubectl rollout restart deployment <deployment>
```

#### Delete evicted pods

```
kubectl get pods | grep Evicted | awk '{print $1}' | xargs kubectl delete pod
```
