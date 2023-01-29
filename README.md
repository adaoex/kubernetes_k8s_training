# Kubernetes (K8s)

## Kind 
kind.sigs.k8s.io

### Kind - Install Go

**Download**
*versão atual disponível em https://go.dev/doc/install*
```
cd ~

wget https://go.dev/dl/go1.19.4.linux-amd64.tar.gz
```

**Remove any previous Go installation**

```
sudo rm -rf /usr/local/go 

sudo tar -C /usr/local -xzf go1.19.4.linux-amd64.tar.gz
```

**Add /usr/local/go/bin to the PATH environment variable**

```
export PATH=$PATH:/usr/local/go/bin
export PATH=$PATH:$HOME/go/bin
```

### Kind - Install Kind
*versão corrente disponível em https://kind.sigs.k8s.io/*

```
go install sigs.k8s.io/kind@v0.17.0
```

```
export PATH=$PATH:/usr/local/go/bin
```

```
kind create cluster
```

## kubectl
https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/


```
~ kubectl cluster-info
```
	kubectl cluster-info
	Kubernetes control plane is running at https://127.0.0.1:46473
	CoreDNS is running at https://127.0.0.1:46473/api/v1/namespaces/kube-system/services/kube-dns:dns/proxy
	
	
~ kubectl get nodes


## K8s Multinodes

https://kind.sigs.k8s.io/docs/user/configuration/#nodes


```
cd ./Projects/fc-k8s/

kind create cluster --config=k8s/kind.yaml --name=clusterblog
```

## K8s REPLICASETS

```
kubectl apply -f k8s/replicasets.yaml

kubectl get pods 
kubectl get replicasets

kibectl describe pod <pode-name>
```

## K8s DEPLOYMENT
- Com a criação de um deployment as replicas anteriores são recriadas.
- Sem downtime.

*Problemas (e solução) com Replicasets OLD*

	@Hierarquia: Deployment - Replicaset - Pod

	kind: Replicaset
	kind: Deployment


**Docker**

```
docker build -t adaoex/hello-go:v3 .

docker push adaoex/hello-go:v3

docker run --rm --name hello-go -p 8000:8000 adaoex/hello-go:v3
```



```
kubectl apply -f k8s/deployment.yaml

kubectl get deployment

kubectl get replicasets

kubectl get pods
```

# Service Account

```
kubectl get serviceaccounts

kubectl get api-resources

```
- default (conta padrão)



