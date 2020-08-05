# MetalLB

## Quick Installation

```
kubectl apply -f 01-namespace.yaml
kubectl apply -f 02-metallb.yaml

# On first install only
kubectl create secret generic -n metallb-system memberlist --from-literal=secretkey="$(openssl rand -base64 128)"

# Layer 2 Configuration
kubectl apply -f 03-metallb-config.yaml
```
