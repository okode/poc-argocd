# POC - Github Actions with ArgoCD

## Local Development

Install kubernetes. For the local cluster we can use [Minikube](https://minikube.sigs.k8s.io/docs/start/?arch=%2Fmacos%2Fx86-64%2Fstable%2Fbinary+download).

#### Creating ArgoCD

```bash
minikube start
```
```bash
kubectl create namespace argocd
```
```bash
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml
```

#### Setting up Helm
```bash
curl https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3 | bash
```
```bash
helm repo add stable https://charts.helm.sh/stable
```
```bash
helm repo update
```

#### Build the application
```bash
docker build -t rferrandop/app-poc:latest .
```

#### Push the image
```bash
docker push rferrandop/app-poc:latest
```

