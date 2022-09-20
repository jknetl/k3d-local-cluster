# How to

1. install cert-manager to cert-manager namespace
   1. `kubectl create namespace cert-manager`
   2. `kubectl apply -f https://github.com/cert-manager/cert-manager/releases/download/v1.9.1/cert-manager.yaml`
2. install resources in this folder to the test namespace


Following https://allanjohn909.medium.com/kubernetes-ingress-traefik-cert-manager-letsencrypt-3cb5ea4ee071