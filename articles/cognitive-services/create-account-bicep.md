---
title: Create an Azure Cognitive Services resource using Bicep | Microsoft Docs
description: Create an Azure Cognitive Service resource with Bicep.
keywords: cognitive services, cognitive solutions, cognitive intelligence, cognitive artificial intelligence
services: cognitive-services
author: schaffererin
ms.service: cognitive-services
ms.topic: quickstart
ms.date: 04/29/2022
ms.author: v-eschaffer
ms.custom: subject-armqs, mode-arm
---

# Quickstart: Create a Cognitive Services resource using Bicep

This quickstart describes how to use Bicep to create Cognitive Services.

Azure Cognitive Services are cloud-base services with REST APIs, and client library SDKs available to help developers build cognitive intelligence into applications without having direct artificial intelligence (AI) or data science skills or knowledge. Azure Cognitive Services enables developers to easily add cognitive features into their applications with cognitive solutions that can see, hear, speak, understand, and even begin to reason.

Create a resource using Bicep. This multi-service resource lets you:

* Access multiple Azure Cognitive Services with a single key and endpoint.
* Consolidate billing from the services you use.
* [!INCLUDE [terms-azure-portal](./includes/quickstarts/terms-azure-portal.md)]

[!INCLUDE [About Bicep](../../includes/resource-manager-quickstart-bicep-introduction.md)]

## Prerequisites

* If you don't have an Azure subscription, [create one for free](https://azure.microsoft.com/free/cognitive-services).

## Review the Bicep file

The Bicep file used in this quickstart is from [Azure Quickstart Templates](https://azure.microsoft.com/resources/templates/cognitive-services-universalkey/).

:::code language="bicep" source="~/quickstart-templates/quickstarts/microsoft.cognitiveservices/cognitive-services-universalkey/main.bicep":::

One Azure resource is defined in the Bicep file:
* [Microsoft.CognitiveServices/accounts](/azure/templates/microsoft.cognitiveservices/accounts): creates a Cognitive Services resource.

## Deploy the Bicep file

1. Save the Bicep file as **main.bicep** to your local computer.
1. Deploy the Bicep file using either Azure CLI or Azure PowerShell.

    # [CLI](#tab/CLI)

    ```azurecli
    az group create --name exampleRG --location eastus
    az deployment group create --resource-group exampleRG --template-file main.bicep
    ```

    # [PowerShell](#tab/PowerShell)

    ```azurepowershell
    New-AzResourceGroup -Name exampleRG -Location eastus
    New-AzResourceGroupDeployment -ResourceGroupName exampleRG -TemplateFile ./main.bicep
    ```

    ---

    When the deployment finishes, you should see a message indicating the deployment succeeded.

## Review deployed resources

Use the Azure portal, Azure CLI, or Azure PowerShell to list the deployed resources in the resource group.

# [CLI](#tab/CLI)

```azurecli-interactive
az resource list --resource-group exampleRG
```

# [PowerShell](#tab/PowerShell)

```azurepowershell-interactive
Get-AzResource -ResourceGroupName exampleRG
```

---

## Clean up resources

When no longer needed, use the Azure portal, Azure CLI, or Azure PowerShell to delete the resource group and its resources.

# [CLI](#tab/CLI)

```azurecli-interactive
az group delete --name exampleRG
```

# [PowerShell](#tab/PowerShell)

```azurepowershell-interactive
Remove-AzResourceGroup -Name exampleRG
```

---

If you need to recover a deleted resource, see [Recover deleted Cognitive Services resources](manage-resources.md).

## See also

* See **[Authenticate requests to Azure Cognitive Services](authentication.md)** on how to securely work with Cognitive Services.
* See **[What are Azure Cognitive Services?](./what-are-cognitive-services.md)** to get a list of different categories within Cognitive Services.
* See **[Natural language support](language-support.md)** to see the list of natural languages that Cognitive Services supports.
* See **[Use Cognitive Services as containers](cognitive-services-container-support.md)** to understand how to use Cognitive Services on-prem.
* See **[Plan and manage costs for Cognitive Services](plan-manage-costs.md)** to estimate cost of using Cognitive Services.
