## Prerequisites

- EKS cluster with ArgoCD installed.
- `kubectl` configured to access the cluster.
- ArgoCD running in `infra-tools` namespace.
- Helm chart for MLflow available or path configured in the Application.

## Clone the repo:

```bash
git clone https://github.com/SergiiGoncharov13/goit-argo.git
cd goit-argo
```

## Apply the ArgoCD Application:
```bash
kubectl apply -f application.yaml
kubectl get applications -n infra-tools
kubectl get pods -n mlflow
```

## Apply the ArgoCD Application:

```bash
kubectl -n infra-tools get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d; echo
kubectl port-forward svc/argocd-server -n infra-tools 8080:443
```

Open `https://localhost:8080` in your browser. <br>
Login with username `admin` and the `password` above.
