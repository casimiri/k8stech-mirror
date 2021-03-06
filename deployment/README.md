# Kubernetes resources
## Cluster information
```
kubectl cluster-info
kubectl version
kubectl get nodes
```
## Run a Pod
```
kubectl run myapp --image rinaahm/k8s_demo --dry-run=client -o yaml > myapp.yaml
kubectl apply -f myapp.yaml
kubectl get pods
kubectl describe pod myapp
kubectl exec -it myapp -- sh
kubectl delete pod myapp
```
## Deployment
```
kubectl create deploy appdeploy --image nginx --replicas=1  --dry-run=client -o yaml > app-deploy.yaml
kubectl apply -f app-deploy.yaml
kubectl get deploy
kubectl scale deploy appdeploy --replicas 5
kubectl scale deploy appdeploy --replicas 2
```
## Service
```
kubectl expose appdeploy --type IPCluster --dry-run=client -o yaml > app-service.yaml
kubectl apply -f app-service.yaml
```
## Ingress Controller
```
helm repo add ingress-nginx https://kubernetes.github.io/ingress-nginx
helm repo update
helm install ingress-nginx ingress-nginx/ingress-nginx
```
## Ingress
```
kubectl apply -f ingress-app.yaml
kubectl get ingress
```
## Config Map
```
kubectl create cm dburl --from-literal URL=db --dry-run=client -o yaml >configMap.yaml
kubectl apply -f configMap.yaml
```
## Secret
```
kubectl create secret generic pwdsecret --from-literal password=1234 --dry-run=client -o yaml > secret.yaml
```


## Container Image

Start with following image:

.NET Core Preview
[rinaahm/k8s_demo](https://hub.docker.com/repository/docker/rinaahm/k8s_demo)

.NET Core Stable
[rinaahm/techsparkapp:v1](https://hub.docker.com/repository/docker/rinaahm/techsparkapp)
