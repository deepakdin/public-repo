## References
  - https://azure.microsoft.com/en-us/products/kubernetes-service/
  - https://azure.microsoft.com/en-us/pricing/details/kubernetes-service/
  - https://learn.microsoft.com/en-us/azure/aks/free-standard-pricing-tiers  
  - https://azure.microsoft.com/en-us/resources/cloud-computing-dictionary/what-is-kubernetes/

  - https://learn.microsoft.com/en-us/azure/aks/
  - https://learn.microsoft.com/en-us/azure/aks/intro-kubernetes
  - https://learn.microsoft.com/en-us/azure/aks/quotas-skus-regions
  - https://learn.microsoft.com/en-us/azure/aks/release-tracker
  - https://learn.microsoft.com/en-us/azure/aks/supported-kubernetes-versions
  - https://learn.microsoft.com/en-us/azure/aks/integrations

  - https://learn.microsoft.com/en-us/azure/aks/concepts-clusters-workloads

  - Samples
    - https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-cli
    - https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-azd
    - https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-portal
    - https://learn.microsoft.com/en-us/azure/aks/learn/quick-kubernetes-deploy-terraform

    - https://learn.microsoft.com/en-us/azure/aks/quickstart-helm
    - https://learn.microsoft.com/en-us/azure/aks/quickstart-dapr
    - https://learn.microsoft.com/en-us/azure/aks/draft-devx-extension-aks
    - https://learn.microsoft.com/en-us/azure/aks/quickstart-event-grid

    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-app
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-prepare-acr
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-cluster
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-deploy-application
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-scale
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-app-update
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-upgrade-cluster
    - https://learn.microsoft.com/en-us/azure/aks/learn/tutorial-kubernetes-workload-identity

  - Architecture
    - https://learn.microsoft.com/en-us/azure/architecture/browse/?products=azure-kubernetes-service

    - https://learn.microsoft.com/en-us/azure/architecture/guide/aks/aks-cicd-azure-pipelines
    - https://learn.microsoft.com/en-us/azure/architecture/guide/aks/aks-cicd-github-actions-and-gitops
    - https://learn.microsoft.com/en-us/azure/architecture/reference-architectures/containers/aks-start-here

  - Node Pools
    - https://learn.microsoft.com/en-us/azure/aks/create-node-pools
    - https://learn.microsoft.com/en-us/azure/aks/manage-node-pools
    - https://learn.microsoft.com/en-us/azure/aks/resize-node-pool
    - https://learn.microsoft.com/en-us/azure/aks/start-stop-nodepools

    - https://learn.microsoft.com/en-us/azure/aks/use-azure-linux

  - Private Cluster
    - Create a private Azure Kubernetes Service (AKS) cluster
    - https://learn.microsoft.com/en-us/azure/aks/access-private-cluster

  - Cluster Upgrade
    - https://learn.microsoft.com/en-us/azure/aks/supported-kubernetes-versions
    - https://learn.microsoft.com/en-us/azure/aks/upgrade-cluster

  - Networking
    - https://learn.microsoft.com/en-us/azure/aks/concepts-network

  - Security
    - https://learn.microsoft.com/en-us/azure/aks/concepts-security
    - https://learn.microsoft.com/en-us/azure/aks/concepts-identity

    - https://learn.microsoft.com/en-us/azure/aks/enable-authentication-microsoft-entra-id

  - Monitoring
    - https://learn.microsoft.com/en-us/azure/aks/monitor-aks

  - Ingress
    - https://learn.microsoft.com/en-us/azure/aks/ingress-basic

  - Sacling
    - https://learn.microsoft.com/en-us/azure/aks/concepts-scale
    - https://learn.microsoft.com/en-us/azure/aks/tutorial-kubernetes-scale
    - https://learn.microsoft.com/en-us/azure/aks/cluster-autoscaler

  - Storage
	- https://docs.microsoft.com/en-us/azure/aks/concepts-storage
	- https://docs.microsoft.com/en-us/azure/aks/operator-best-practices-storage
	- https://learn.microsoft.com/en-us/azure/aks/azure-csi-disk-storage-provision
	- https://learn.microsoft.com/en-us/azure/aks/azure-csi-files-storage-provision

  - DevOps
    - https://learn.microsoft.com/en-us/azure/aks/devops-pipeline
    - https://learn.microsoft.com/en-us/azure/aks/kubernetes-action

  - Tools
    - https://marketplace.visualstudio.com/items?itemName=ms-kubernetes-tools.vscode-kubernetes-tools

  - Helm
    - https://learn.microsoft.com/en-us/azure/aks/quickstart-helm?tabs=azure-cli

  - MISC
      - https://learn.microsoft.com/en-us/cli/azure/aks

      - https://learn.microsoft.com/en-us/azure/aks/node-auto-repair

      - https://learn.microsoft.com/en-us/azure/architecture/example-scenario/gitops-aks/gitops-blueprint-aks

      - https://azure.microsoft.com/en-us/solutions/kubernetes-on-azure/deployment-strategy/


## Install Azure CLI and Azure AKS CLI
```t
# Install Azure CLI
https://learn.microsoft.com/en-us/cli/azure/install-azure-cli

# Install/Update Azure AKS CLI
- https://learn.microsoft.com/en-us/cli/azure/aks#az-aks-install-cli

az aks install-cli # Install latest version
az aks install-cli --client-version 1.27.7 # Install specific version

    - Download and install kubectl, the Kubernetes command-line tool.
    - Download and install kubelogin, a client-go credential (exec) plugin implementing azure authentication.
    - Add the installation path to the PATH environment variable so that command can be searched during execution.    
    - If we do not want to install `Azure AKS CLI`, alternatively we can inatll both `kubectl` and `kubelogin` manually and add the installation path to the PATH environment variable manually.
        https://kubernetes.io/docs/tasks/tools/install-kubectl-windows/
        https://kubernetes.io/docs/tasks/tools/install-kubectl-linux/
        https://kubernetes.io/docs/tasks/tools/install-kubectl-macos/

        https://azure.github.io/kubelogin/install.html

        Path Command - CMD: set PATH=%PATH%;C:\xxx\.azure-kubectl
        Path Command - Powershell: $env:path += 'C:\xxx\.azure-kubectl'
   - You must use a kubectl version that is within one minor version difference of your cluster. For example, a v1.29 client can communicate with v1.28, v1.29, and v1.30 control planes.

# Verify the `Azure CLI` Version Information
az version

# Verify the `Kubectl` Version Information
kubectl version
kubectl version --short
kubectl version --output=yaml

# Verify the `kubelogin` Version Information
kubelogin --version
```

## Authenticate to Azure using the Azure CLI
```t
# Login to Azure
az login

# List Azure Subscriptions
az account list

# Set the Current Subscription
az account set --subscription="SUBSCRIPTION_ID"
az account set --subscription 'xxx'

# Verify the Current Subscription
az account show
```

## Setup AKS Cluster and Credential
### Create AKS Cluster
```t
# Create Resource Group
az group create -n <resource-group-name> --location <location-name>
az group create -n learncloud-aks-rg --location eastasia

# Create AKS Cluster
az aks create -g <resource-group> -n <cluster-name> --enable-managed-identity --node-count 1 --generate-ssh-keys

az aks create -g learncloud-aks-rg -n learncloud-aks --enable-managed-identity --node-count 1 --generate-ssh-keys

az aks create -g learncloud-aks-rg -n learncloud-aks --enable-managed-identity --node-count 1 --enable-cluster-autoscaler --min-count 1 --max-count 3 --enable-addons monitoring --generate-ssh-keys

# Connect to AKS Cluster
az aks get-credentials -g learncloud-aks-rg -n learncloud-aks
```

### Create AKS Cluster - Azure CNI
```t
# Create Resource Group
az group create -n learncloud-aks-azcni-rg --location eastasia

# Create AKS Cluster
az aks create -g learncloud-aks-azcni-rg -n learncloud-aks-azcni --enable-managed-identity --node-count 2 --network-plugin azure --generate-ssh-keys

# Connect to AKS Cluster
az aks get-credentials -g learncloud-aks-azcni-rg -n learncloud-aks-azcni
```

### Connect to AKS Cluster - Azure CLI - Local Machine
```t
# Configure kubectl to connect to your AKS cluster
az aks get-credentials -g <resource-group> -n <cluster-name>
az aks get-credentials -g learncloud-aks-rg -n learncloud-aks

    - Configure kubectl to connect to your Kubernetes cluster.
    - Downloads credentials and configures the Kubernetes CLI to use them.
    - Uses `~/.kube/config`, the default location for the Kubernetes configuration file. Specify a different location for your Kubernetes configuration file using --file argument.

# Verify the connection to your AKS cluster
kubectl get nodes
```

### Connect to AKS Cluster - Azure CLI - Cloud Shell
- Go to https://shell.azure.com

```t
# Configure kubectl to connect to your AKS cluster
az aks get-credentials -g <resource-group> -n <cluster-name>
az aks get-credentials -g learncloud-aks-rg -n learncloud-aks

# Verify the connection to your AKS cluster
kubectl get nodes
```

### Explore the AKS cluster on Azure Management Console
- Explore the following features on high-level
- **Overview**
  - Activity Log
  - Access Control (IAM)
  - Security
  - Diagnose and solve problems
  - Microsoft Defender for Cloud
- **Kubernetes Resources**  
  - Namespaces
  - Workloads
  - Services and Ingress
  - Storage
  - Configuration
- **Settings**
  - Node Pools
  - Cluster Configuration
  - Extensions + Applications
  - Backup (preview)
  - Open Service Mesh
  - GitOps
  - Automated Deployments (preview)
  - Policies
  - Properties
  - Locks
- **Monitoring**
  - Insights
  - Alerts
  - Metrics
  - Diagnostic Settings
  - Advisor Recommendations
  - Logs
  - Workbooks
- **Automation** 
  - Tasks
  - Export Template 
- **Infrastructure resource group(MC_xxx)** 
  - VNet
  - Route Table
  - NSG
  - Load balancer (Load balance traffic to service) 
  - Public IP (1 IP per LB Frontend ip configuration)
  - VMSS (Node pool VMs)
  - Managed Identity (Attached to VMSS)


## Attach ACR with AKS
- When using ACR with AKS, you need to establish an authentication mechanism.
- Configuring the required permissions between ACR and AKS can be accomplished using the Azure CLI, Azure PowerShell, and Azure portal.
- The AKS to ACR integration assigns the AcrPull role to the Azure Active Directory (Azure AD) managed identity associated with the agent pool in your AKS cluster.

### Configure authentication between ACR and AKS using Azure CLI
```t
# Attach using acr-name
az aks update -n <cluster-name> -g <resource-group> --attach-acr <acr-name>
az aks update -n learncloud-aks -g learncloud-aks-rg --attach-acr learncloudacr

# Attach using acr-resource-id
az aks update -n <cluster-name> -g <resource-group> --attach-acr <acr-resource-id>
```

## MISC
---

## AKS Administration Activities
- AKS Cluster Provisioning through IaC
	- Networking Configuration
	- Security Configuration
	- Nodepool Configuration
	- High Availability
- Autoscaling Configuration and Management
- Upgrade AKS Kubernetes version
	- Automatic Upgrade
	- Manual Upgrade
	- Blue/Green Deployment
- Upgrade AKS node images
- Kubernetes RBAC Management
- Storage Provisioning/Management
