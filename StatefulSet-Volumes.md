# Stateful & Stateless

## Kubernetes Persistent Volume - PV.yaml

Claim > StorageClass > BlockStorage


```
kubectl get storageclass

kubectl apply -f k8s/pvc.yaml

kubectl get pvc

```

Escalando manualmente: 

```
kubectl scale statefulset mysql --replica=4
```

## Headless service

```
kubectl apply -f k8s/statefulset.yaml

kubectl get -f k8s/mysql-service-h.yaml

kubectl get svc
```

Pingando: 

````
ping mysql-h

ping mysql-0.mysql-h

ping mysql-1.mysql-h
```


