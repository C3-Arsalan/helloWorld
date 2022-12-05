## Platform deployment

+ Authenticate using the Azure CLI
```bash
az login
```
+ Set the content
```bash
 az account set --subscription "<SUBSCRIPTION_ID>"
```
+ Create a Service Principal
```bash
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<SUBSCRIPTION_ID>"
```
+ Set the environment variables
```bash
 export ARM_CLIENT_ID="<APPID_VALUE>"
 export ARM_CLIENT_SECRET="<PASSWORD_VALUE>"
 export ARM_SUBSCRIPTION_ID="<SUBSCRIPTION_ID>"
 export ARM_TENANT_ID="<TENANT_VALUE>"
 ```
+ Set up and initialize the Terraform workspace
```bash
git clone 
```
+ Navigate to the cloned folder and initialise the Terraform
```bash
terraform init
```
+ Provision the AKS cluster
```bash
terraform apply
```
## Application Deployment
+ Configure kubectl
```bash
az aks get-credentials --resource-group $(terraform output -raw resource_group_name) --name $(terraform output -raw kubernetes_cluster_name)
```
