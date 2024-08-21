# Nodeport Service

#nodeport.yaml
```sh
apiVersion: v1
kind: Service
metadata:
  name: nodeport-svc
  labels:
    env: demo
spec:
  type: NodePort
  selector:
    env: demo
  ports:
  - nodePort: 30001
    port: 80
    targetPort: 80
```

#create nodeport service
```sh
kubectl get pods --show-labels
kubectl explain service
kubectl create -f nodeport.yaml
kubectl get service
kubectl get svc
```

#get the ip address of the pod
```sh
kubectl get pods -o wide
```
