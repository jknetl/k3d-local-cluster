# Instructions

[based on Argo's getting started](https://argo-cd.readthedocs.io/en/stable/)

1. Install argocd to the cluster

    kubectl create namespace argocd
    wget https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
    kubectl apply -n argocd -f install.yaml

2. Install Argo CLI (dowload it binary in https://github.com/argoproj/argo-cd/releases/)
3. Make ArgoCD available outside cluster
   - ingress
   - LoadBalancer
   - port-forward - temporarily used
     - kubectl port-forward svc/argocd-server -n argocd 8080:443

Now its installed, you can configure credentials:

    # Get crecdentials for admin
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
    argocd login <ARGOCD_SERVER>
    argocd account update-password


## Configure ingress

1. To argocd-cmd-params-cm ConfigMap add following key:
```
  server.insecure: "true"
```
2. Apply ingressroute.yaml

