# Pod in Kubernetes Imperative/Declarative
#Create an Nginx pod through kubectl imperative way
```sh
  kubectl run nginx-pod --image=nginx:latest
  kubectl get pods
```
#pod.yaml
```sh
# This is a sample pod yaml
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
  labels:
    env: demo
    type: frontend
spec:
  containers:
    - name: nginx-container
      image: nginx
      ports:
      - containerPort: 80
```

```sh
kubectl explain pod
kubectl create -f pod.yaml
kubectl get pods
kubectl delete pod nginx-pod
kubectl apply -f pod.yaml
kubectl describe pod nginx-pod
```

#directly edit a pod in the cluster itself
```sh
kubectl edit pod nginx-pod
```

#connect with the pod using exec/sh
```sh
kubectl exec -it nginx-pod -- sh 
```

#dry run to generate/create yaml files without manual typing
```sh
kubectl run nginx --image=nginx --dry-run=client
kubectl run nginx --image=nginx --dry-run=client -o yaml
kubectl run nginx --image=nginx --dry-run=client -o yaml > pod-new.yaml
```
