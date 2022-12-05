# helloWorld Assignment
This repo contains deployment instruction, required helm chart, and platform deployment code to simply deploy a helloWord web.

## Assumption
1. The main cost for this project is time, and I spend 2hr to provide this application. Hence, I simplified the project by:
- ignoring the branches or version control in repo. Commit everything to a test branch;
- not creating CI/CD pipeline;
- not using key vault to pass the values;
- using sample code to deploy platform, not any actual parameters;
- not deploying the code in an actual env.;
- not changing the helm chart values to reflect a better, safer, and more reliable application;
- considering a very simple health check such as running a curl script on a crown job through a Linux box and not checking the SSL cert, server load, recovery plan, etc.;
- considering a simple architecture but not a full platform deployment of Vnet, AppGW, SG, etc.;
2. Using Terraform code to deploy a simple AKS cluster in Azure;
3. Using a simple helm chart to deploy helloWord application on k8s;

## Prerequisites
1. Free account in Azure
2. Terraform
3. az CLI
4. Helm and Kubectl
