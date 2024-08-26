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

#creating pod within demo namespace
```sh
kubectl create deploy nginx-demo --image=nginx -n demo
kubectl get deploy -n demo
```

#default namespace
```sh
kubectl create deploy nginx-test --image=nginx
kubectl get pods
```

#connect to other pods
```sh
kubectl get pods
kubectl exec -it nginx-test-5b77bfd686-k4f45 -- sh

kubectl get pods -n=demo
kubectl exec -it nginx-demo-5b77bfd686-k4f45 -- sh
kubectl exec -it nginx-demo-cccbdc67f-xvhzs -n=demo -- sh
kubectl get pods -n=demo -o wide
#curl 10.244.2.7
```

#scale the pods
```sh
kubectl scale --replicas=3 deploy/nginx-demo -n=demo
```
