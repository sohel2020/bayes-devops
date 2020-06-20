# Istio Installation

## Prerequisites:
1. Helm >= 3.2.4

## Helm install 

```bash
brew install helm
```
## Istio Install 

```bash
curl -L https://istio.io/downloadIstio | ISTIO_VERSION=1.4.3 sh -
cd istio-1.4.3
chmod +x bin/istioctl
mv bin/istioctl /usr/local/bin
kubectl create namespace istio-system
helm install istio-init --namespace istio-system install/kubernetes/helm/istio-init
helm install istio  --namespace istio-system install/kubernetes/helm/istio
```