# argocd-cluster-base-apps
This repo contains cluster base applications for argocd cluster bootstraping 

# ArgoCD Initial Installation

- Create Namespace
kubectl apply -f argocd/namespace.yaml

- Apply argocd manifests 
kubectl apply -f argocd/resources.yaml

- Once installed you can get into the UI by setting a port forward 
kubectl port-forward svc/argocd-server -n argocd 8080:443

Point your browser to http://localhost:8080

- Get default admin credentials 
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d




