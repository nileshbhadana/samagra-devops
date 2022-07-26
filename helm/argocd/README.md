# ArgoCD Helm Chart

### Installation


Helm Version: `v3.7.0`

K8s Version: `v1.21.11`

```console
    $ helm repo add argo https://argoproj.github.io/argo-helm
    $ helm upgrade -install argocd argo/argo-cd  -n argocd  --create-namespace -f helm/argocd/values.yaml ./helm/argocd/
```
---

### Retrieve Admin Credentials

```console
    $ kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
```

---

### Access Argo Console

Run the following command in your terminal:

```console
    $ kubectl port-forward service/argocd-server -n argocd 8080:80
```

Now, Open your web browser and open `http://localhost:8080` and at login page enter Username: `admin` and Password: `<Your Admin Password>`