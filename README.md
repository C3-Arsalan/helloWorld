# helloWorld Assignment
This repo contains deployment instruction, required helm chart, and platform deployment code to simply deploy a helloWorld web.

## Assumption
1. The main cost for this project is time, and I budget the project for 3.5hr to provide this application. Hence, I simplified the project by:
- Considering a simple architecture but Not a full platform deployment of Vnet, AppGW, Ingress, SG, etc.;
- Not creating CI/CD pipeline;
- Not using key vault to pass the values;
- Not changing the helm chart values to reflect a better, safer, and more reliable application;
- Considering a very simple health check such as running a curl script on a cron job through a Linux box and Not checking the SSL cert, server load, recovery plan, Prometheus deployment, monitoring deployment in the platform, etc.;
2. Using Terraform to deploy a simple AKS cluster in Azure;
3. Using a simple helm chart to deploy helloWorld application on k8s;

## Prerequisites
1. Free account in Azure
2. Terraform
3. az CLI
4. Helm and Kubectl
