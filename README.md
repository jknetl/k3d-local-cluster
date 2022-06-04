# Local kubernetes cluster using k3d


1. Create k3d cluster with ingress enabled:
    ``` k3d cluster create local --api-port 6550 --agents 1  -p "80:80@loadbalancer" -p "443:443@loadbalancer" ```
