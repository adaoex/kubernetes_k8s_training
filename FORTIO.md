# Teste de stresse com fortio

## HPA - Horizontal Pod Autoscaler

kubectl apply -f k8s/metrics-server.yaml



## Fortio
https://github.com/fortio/fortio

Subindo um POD com fortio (executando 800 queries por segundos,por 120 segundos, 70 conexões): 

kubectl run -it fortio --rm --image=fortio/fortio -- load -qps 800 -t 120s -c 70 "http://10.244.0.11:8000/healthz"
kubectl run -it fortio --rm --image=fortio/fortio -- load -qps 800 -t 120s -c 70 "http://goserver-service/healthz"



API: 

kubectl apply -f k8s/deployment.yaml

kubectl apply -f k8s/hpa.yaml



Assistindo: 

watch -n1 kubectl get hpa
