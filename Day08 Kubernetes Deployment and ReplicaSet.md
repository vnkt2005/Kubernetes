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
