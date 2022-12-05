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
git clone https://github.com/arsalan-ansari-81/helloWorld.git
```
+ Navigate to the cloned folder/terraformCode and initialise and plan the Code
```bash
terraform init
terraform plan
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
+ Helm deploy the application
```bash
helm create helloworld
```
> Update the values.yaml to change the service to NodePort to make the service available outside of k8s, then deploy the chart.
```bash
helm install assignment-helloWordWeb helloworld
```
+ getting the service port and IP access
```bash
kubectl get service
```
## Health monitor
+ Config a crontab to run a job every 10m to curl the web and log the result.
```bash
crontab <<'EOF'
SHELL=/bin/bash
#min hr md mo wkday command
*/10 *  *  *  *     curl -sSf 'http://<k8sIP>:<ServicePort>' > /dev/null && echo "success"
EOF
```
