# Local kubernetes cluster using k3d


1. Create k3d cluster with ingress enabled:
    ``` k3d cluster create --api-port 6550 -p "8888:80@loadbalancer" local ```
