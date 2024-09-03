# EKS End-to-End Project
<p>1. Ensure kubectl is installed on your laptop. 
If kubectl is not installed please goto <a href="https://github.com/vnkt2005/Kubernetes/blob/main/Prerequisites.md">Prerequisites.md</a>.</p>

<p>2. Ensure eksctl is installed on your laptop. 
If eksctl is not installed please goto <a href="https://github.com/vnkt2005/Kubernetes/blob/main/Prerequisites.md">Prerequisites.md</a>.</p>

<p>
  3. To install AWS CLI on Windows, use AWS official website address <a href="https://docs.aws.amazon.com/cli/v1/userguide/install-windows.html">https://docs.aws.amazon.com/cli/v1/userguide/install-windows.html</a>
</p>

<p>
  4. Configure AWS CLI using following command. aws configure command will ask you to provide AWS access key ID, AWS secret access key, default region code and default output format(json).
</p>

 ```sh
 aws configure
 ```

<p>
  5. Create EKS Cluster using command eksctl.
</p>

```sh
eksctl create cluster --name demo-cluster-1 --region ap-south-1 --fargate
eksctl delete cluster --name demo-cluster-1 --region ap-south-1
```

<p>
  6. Configuring kubectl for eks.
</p>

```sh
aws eks update-kubeconfig --name demo-cluster-1 --region ap-south-1
kubectl get nodes
```

# Deployment of application.

<p>
  7. Creating forgate profile for new namespace.
</p>


