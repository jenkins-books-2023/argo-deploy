# ArgoCD auto deploy

---
## Setup
### ArgoCD server
```argocd setup
kubectl create namespace argocd
kubectl apply -f applications/argocd-server/. -n argocd
```
### ArgoCD applications
```
kubectl apply -f applications/.
```

### Get ArgoCD password
```
kubectl -n argocd get secret argocd-initial-admin-secret \
    -o jsonpath="{.data.password}" | base64 -d; echo
```
