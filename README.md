# Gitops and ArgoCD Lab

[Things I have to do](image.png)
[Lecture Notes](https://petal-estimate-4e9.notion.site/Gitops-and-argocd-1e97dfd10735809c9f81d1307f92771c)

### Install ArgoCD in a namespace and apply the manifests using the official repository yaml file for the latest stable version to locally install ArgoCD
```bash
kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

### Access the argocd ui using port forwarding
```bash
kubectl port-forward svc/argo-cd-argocd-server 8080:80
```
### Get the password for the argo-cd admin user
```bash
# Get the password for the argo-cd admin user
kubectl get secret argocd-initial-admin-secret -n argocd -o jsonpath="{.data.password}" | base64 --decode
# echo "encoded_password" | base64 --decode
```

## ArgoCD

### ArgoCD vs GitOps

### ArgoCD vs Flux

### ArgoCD vs Helm

### ArgoCD vs Kustomize