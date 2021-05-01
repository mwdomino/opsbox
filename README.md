# opsbox
Opsbox runs CI and configuration management, orchestrated by Jenkins. To deploy on a k3s cluster follow the below instructions:

## deploy cert-manager
We use `cert-manager` to automatically retrieve and store TLS certificates for web services.

``` sh
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.3.1/cert-manager.yaml
kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.3.1/cert-manager.crds.yaml
```

## deploy manifests 
```
kubectl apply -f manifests/
```

#### Deploys the following:
* Jenkins handles orchestrating the different management tools like `terraform`, `ansible`, and `kubectl` 

