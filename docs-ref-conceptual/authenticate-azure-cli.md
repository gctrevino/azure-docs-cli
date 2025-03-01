---
title: Sign in with Azure CLI — Login and Authentication | Microsoft Docs
description: Learn the different authentication types for your Azure CLI login — sign in with Azure CLI automatically, locally, or interactively using the az login command.
author: jiasli
ms.author: jiasli
manager: yonzhan
ms.date: 04/09/2024
ms.topic: conceptual
ms.service: azure-cli
ms.tool: azure-cli
ms.custom: devx-track-azurecli, seo-azure-cli
keywords: az login, authentication types , authentication methods, azure, cli login, az login powershell, cli login, sign in 
---

# Authenticate to Azure using Azure CLI

The Azure CLI supports several authentication methods. Restrict sign-in permissions for your use case to keep your Azure resources secure.

## Sign into Azure with Azure CLI

There are five authentication options when working with the Azure CLI:

| Authentication method | Advantage |
|-|-|
| [Azure Cloud Shell](/azure/cloud-shell/overview) | Azure Cloud Shell automatically logs you in and is the easiest way to get started.
| [Sign in interactively](./authenticate-azure-cli-interactively.md) | This is a good option when learning Azure CLI commands and running the Azure CLI locally. Login through your browser with the [az login](/cli/azure/reference-index#az-login) command.
| [Sign in interactively (preview)](./authenticate-azure-cli-preview.md) | This option prompts you to pick your subscription when using the [az login](/cli/azure/reference-index#az-login) command.
| [Sign in using a service principal](./authenticate-azure-cli-service-principal.md) | When you write scripts, using a service principal is the recommended approach. You grant just the appropriate permissions needed to a service principal keeping your automation secure.
| [Sign in with a managed identity](./authenticate-azure-cli-managed-identity.md) | A common challenge for developers is the management of secrets, credentials, certificates, and keys used to secure communication between services. Using a managed identity eliminates the need for you to manage these credentials.
| [Sign in using Web Account Manager (WAM)](./authenticate-azure-cli-web-account-manager.md) | WAM is a Windows 10+ component that acts as an authentication broker. WAM provides enhanced security and enhancements are shipped with Windows.

## Find or change your current subscription

After you sign in, CLI commands are run against your default subscription. If you have multiple subscriptions, change your default subscription using `az account set --subscription`.

```azurecli-interactive
az account set --subscription "<subscription ID or name>"
```

Another option is to use the [authentication preview](./authenticate-azure-cli-preview.md) of Azure CLI [2.59.0](./release-notes-azure-cli.md#april-02-2024). The authentication preview provides a tenant and subscription list at time of login, and you're prompted to select a default subscription.

To learn more about managing Azure subscriptions, see [How to manage Azure subscriptions with the Azure CLI](./manage-azure-subscriptions-azure-cli.md).

## Refresh tokens

[!INCLUDE [refresh-token](includes/refresh-token.md)]

> [!NOTE]
> Depending on your sign in method, your tenant may have Conditional Access policies that restrict your access to certain resources.

## See also

* [Azure CLI Onboarding cheat sheet](./cheat-sheet-onboarding.md)
* [Manage Azure subscriptions with the Azure CLI](./manage-azure-subscriptions-azure-cli.md)
* Find Azure CLI [samples](./samples-index.md) and [published articles](./reference-docs-index.md)
