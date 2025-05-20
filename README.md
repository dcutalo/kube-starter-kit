# Welcome to My Project
## Installation
### Step 1: Clone the Repo
```bash
git clone <repo>
```
### Step 2: Install local dev tools
```bash
brew install kubectl
kubectl version --client
```
```bash
brew install helm
helm version
```
```bash
brew tap hashicorp/tap
```
```bash
brew install hashicorp/tap/terraform
terraform version
```
```bash
brew install kubectx
kubectx
```
#### Optional useful for context switching
```bash
brew install kubens
```
### Step 3: Spin up local cluster with kind
```bash
kind create cluster --name dev-lab --config kind-cluster.yaml
```
#### How to stop the cluster
```bash
kind delete cluster --name dev-lab
```
#### How to get all clusters
```bash
kind get clusters
```
### Verify the Cluster is Running
```bash
kubectl cluster-info --context kind-dev-lab
kubectl get nodes
```
### We can use kubectx later to switch clusters
#### kubectx <cluster_name> || kubectx to view cluster names
### 4. Apply metrics-server
#### This is required for autoscaling (HPA, resource metrics, etc.)
```bash
kubectl apply -f metrics-server.yaml
```
