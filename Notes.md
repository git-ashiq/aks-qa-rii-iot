#Install the aks-preview Azure CLI

# Install the aks-preview extension
az extension add --name aks-preview

# Update the extension to make sure you have the latest version installed
az extension update --name aks-preview

#Update an existing AKS cluster with Azure CNI
az aks update -g $MY_RESOURCE_GROUP -n $MY_CLUSTER --enable-pod-identity

#Upgrade an existing AKS cluster with Azure Key Vault Provider for Secrets Store CSI Driver support
az aks enable-addons --addons azure-keyvault-secrets-provider --enable-secret-rotation --rotation-poll-interval 4m --name $AKS_CLUSTRE_NAME --resource-group rii-qa