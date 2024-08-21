# Nodeport

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

```sh
kubectl get pods --show-labels
kubectl explain service
kubectl create -f nodeport.yaml
```
