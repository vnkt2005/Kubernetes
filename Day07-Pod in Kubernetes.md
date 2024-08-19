# Pod in Kubernetes Imperative/Declarative
#Create an Nginx pod through kubectl imperative way
```sh
  kubectl run nginx-pod --image=nginx:latest
  kubectl get pods
```
#day7-yaml.yaml
```sh
# This is a sample pod yaml
apiVersion:
kind:
metadata:
spec:
```

```sh
kubectl explain pod
```
