# Kubernetes Deployment, Replication Controller And ReplicaSet
#rc.yaml
```sh
apiVersion:  v1
kind:  ReplicationController
metadata:
  name: nginx-rc
  labels:
    env: demo
spec:
  template:
    metadata:
      labels:
        env: demo
      name: nginx
    spec:
      containers: 
      - image: nginx
        name: nginx
  replicas: 3
```
#create replication controller
```sh
kubectl get pods
kubectl delete pod nginx-pod
kubectl apply -f rc.yaml
kubectl get pods
kubectl get rc
kubectl describe pod nginx-rc-bdf2d
```

#rs.yaml
```sh
apiVersion:  v1
kind:  ReplicaSet
metadata:
  name: nginx-rs
  labels:
    env: demo
spec:
  template:
    metadata:
      labels:
        env: demo
      name: nginx
    spec:
      containers: 
      - image: nginx
        name: nginx
  replicas: 3
  selector:
    matchLabels:
      env: demo
```
#create replicaset
```sh
kubectl apply -f rs.yaml
kubectl explain rs
kubectl delete rc/nginx-rc
```

#how to make number of replicas = 5
```sh
replicas: 5
kubectl apply -f rs.yaml
```

#live edit replicaset
```sh
kubectl edit rs/nginx-rs
```

#another way to edit number of replicas
```sh
kubectl scale --replicas=10 rs/nginx-rs
```
