## Create namespace for argocd:
```
kubectl create namespace argocd
```

## Install argocd in connected cluster:
```
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

## Get admin password (login: admin)
```
kubectl get secret argocd-initial-admin-secret -n argocd -o yaml
```

## Running argocd by forwaring its main service's ports: argocd-server:
```
kubectl port-forward svc/argocd-server -n argocd 8080:443
```

## Put argocd config:
```
kubectl apply -f application.yaml
```
