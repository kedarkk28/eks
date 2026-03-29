# EKS Cluster Deployment

## Step by step deployment
 
### 1. Initialise Terraform.
 
Downloads all providers declared in `main.tf`:
 
```bash
terraform init
```
--- 
### 2. Preview what will be created with plan.
 
```bash
terraform plan
```
--- 
### 3. Apply terraform
 
```bash
terraform apply --auto-approve
```
---
### 4. Connect kubectl to the cluster and check the nodes are up.
  
```bash
aws eks update-kubeconfig --region us-east-1 --name quotes-eks
```
 
Verify your 3 worker nodes are Ready:
 
```bash
kubectl get nodes
```
---
### 5. Apply the yaml manifest files

```bash
kubectl apply -f nginx-deployment.yaml
kubectl apply -f nginx-service.yaml
```
---
### 6. Check the resources created

```bash
kubectl get all
```
---
