# Demo

## Create a namespace

```bash
kubectl create namespace kubedaily-demo --dry-run=client -o yaml > namespace.yaml
```

Apply namespace

```bash
kubectl apply -f namespace.yaml
```

```bash
kubectl get namespaces
```

Set the namespace

```bash
kubectl config set-context --current --namespace=kubedaily-demo
```

## Create a deployment

```bash
kubectl create deployment kubedaily-demo --image=dalekurt/rancher-demo --dry-run=client -o yaml > deployment.yaml
```

```bash
kubectl apply -f deployment.yaml
```

## Create a service 

```bash
kubectl expose deployment kubedaily-demo --port=80 --target-port=8080 --type=LoadBalancer --name=kubedaily-demo --dry-run=client -o yaml > service.yaml
```

```bash
kubectl apply -f service.yaml
```

## Scale replica

```bash
kubectl scale --replicas=1 deployment/kubedaily-demo
```
