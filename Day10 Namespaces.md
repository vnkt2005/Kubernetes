# Namespaces
```sh
kubectl get ns
kubectl get all --namespace=kube-system
kubectl get all -n kube-system
kubectl get all -n kube-public
kubectl get all -n kube-node-lease
```

#using default namespace
```sh
kubectl get all
kubectl get all -n default
```

# Creating namespaces
#ns.yaml
```sh
apiVersion: v1
kind: Namespace
metadata:
  name: demo
```
#creating namespace
```sh
kubectl apply -f ns.yaml
kubectl get namespaces
kubectl get ns
```

#create namespace imparative way without ns.yaml file
```sh
kubectl create ns demo
```

#delete namespace
```sh
kubectl delete ns/demo
```
