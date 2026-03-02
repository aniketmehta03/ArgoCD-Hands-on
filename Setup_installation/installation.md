# ArgoCD Setup and Installation

Let's see how we can Setup & Install ArgoCD (UI and CLI) and access via the browser.

---

# Prerequisites

Before starting, ensure you have the following installed on your system:

1. **Docker** → Required for Kind to run containers as cluster nodes.

   ```bash
   sudo apt-get update
   sudo apt install docker.io -y
   sudo usermod -aG docker $USER && newgrp docker
   docker --version

   docker ps
   ```
## **Method : Install ArgoCD using Helm** (recommended for customization/production)

### 1. Add Argo Helm repo

```bash
helm repo add argo https://argoproj.github.io/argo-helm
helm repo update
```

### 2. Create namespace

```bash
kubectl create namespace argocd
```

### 3. Install ArgoCD

```bash
helm install argocd argo/argo-cd -n argocd
```

### 4. Verify installation

```bash
kubectl get pods -n argocd
kubectl get svc -n argocd
```

### 5. Access the ArgoCD UI

Port-forward the service:

```bash
kubectl port-forward svc/argocd-server -n argocd 8080:443 --address=0.0.0.0 &
```

Now open → **[https://<instance_public_ip>:8080](https://<instance_public_ip>:8080)**

### 6. Get initial admin password

```bash
kubectl get secret argocd-initial-admin-secret -n argocd \
  -o jsonpath="{.data.password}" | base64 -d && echo
```

Login with:

* Username: `admin`
* Password: (above output)

---

---

# Step 3: Install ArgoCD CLI (Ubuntu/Linux)

ArgoCD server runs inside Kubernetes, but to interact with it from the terminal you need the **ArgoCD CLI (`argocd`)**.  
This is separate from the server installation.

### 1. Install ArgoCD CLI

```bash
curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
rm argocd-linux-amd64
```

### 2. Verify installation

```bash
# Verify installation
argocd version --client
```

### 3. Login to ArgoCD CLI

```bash
argocd login <instance_public_ip>:8080 --username admin --password <initial_password> --insecure
```

> Note: The --insecure flag is required when using port-forward with self-signed TLS certs.
For production, you’d configure proper TLS certs (then --insecure is not needed).

### 4. Get user info

```bash
argocd account get-user-info
```
