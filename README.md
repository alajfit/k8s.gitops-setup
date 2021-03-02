# K8s Cluster on Digital Ocean

## Steps to setup K8s

1. Create Cluster on Digital Ocean
   1. Manage -> Kubernetes -> Create a Kubernetes Cluster -> Fill in Form -> Create Kubernetes -> Install kubectl and doctl
2. Run the following commands locally
   ```sh
   helm repo add argo https://argoproj.github.io/argo-helm
   helm fetch argo/argo-cd --untar
   cd ./argo-cd
   kubectl create namespace argocd
   helm --namespace argocd --set server.extraArgs="{--insecure}" template . | kubectl apply -n argocd -f -
   ```
3. Pull this repo
