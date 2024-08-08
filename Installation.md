# Kubectl Installation
#Kubectl installation, 
#Google search for install kubectl, 
#Goto website address - https://kubernetes.io/docs/tasks/tools, 
#click install kubectl on windows

#Download kubectl.exe binary file
```sh
  mkdir e:\kubectl
  cd kubectl
  curl.exe -LO "https://dl.k8s.io/release/v1.30.0/bin/windows/amd64/kubectl.exe"
```

#Validate the binary
```sh
  curl.exe -LO "https://dl.k8s.io/v1.30.0/bin/windows/amd64/kubectl.exe.sha256"
  CertUtil -hashfile kubectl.exe SHA256
  type kubectl.exe.sha256
```

#Using powershell to automate the verification
```sh
  $(Get-FileHash -Algorithm SHA256 .\kubectl.exe).Hash -eq $(Get-Content .\kubectl.exe.sha256)
```

#Check the version
```sh
  kubectl version --client
  kubectl version --client --output=yaml
```

# Minikube Installation

#search google for minikube install
#go to official website https://minikube.sigs.k8s.io › docs › start
#to download minikube

```sh
  mkdir e:\minikube
  cd e:\minikube
```

#powershell run as administrator
```sh
  $oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
if ($oldPath.Split(';') -inotcontains 'E:\minikube'){
  [Environment]::SetEnvironmentVariable('Path', $('{0};E:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine)
}
```

#start your cluster
#From a terminal with administrator access (but not logged in as root), run:
```sh
  minikube start
```





