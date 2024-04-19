---
title: Release notes & updates – Azure CLI | Microsoft Docs
description: Learn about the latest Azure Command-Line Interface (CLI) release notes and updates for both the current and beta versions of the CLI.
manager: jasongroce
author: dbradish-microsoft
ms.author: dbradish
ms.date: 04/02/2024
ms.topic: article
ms.service: azure-cli
ms.tool: azure-cli
ms.custom: devx-track-azurecli
keywords: azure cli updates, azure cli notes, azure cli versions
---

# Attachment 3: PR-003521 Azure CLI Release Notes

# Azure CLI release notes

## April 02, 2024

Version 2.59.0

### ACR

* Fix #14768: `az acr login`: Add environment variable for docker command

### ACS

* `az aks create`: Add flag `--enable-app-routing` to enable app routing
* `az aks approuting`: Add command group to handle enable/disable/update of the app routing addon
* `az aks approuting zone`: Add command group to handle add/delete/update/list actions of DNS zone resources associated to the approuting addon
* `az aks create/update`: Introduce changes for Azure container storage in ACS CLI

### AD

* `az ad`: Rename Azure Active Directory to Microsoft Entra ID

### AKS

* `az aks create`: Add optional parameter `--revision` to set revision for the Azure Service Mesh addon while creating AKS cluster
* `az aks mesh get-upgrades`: Fix command failure with a traceback if ASM addon is disabled
* `az aks create/update`: Enable mooncake support for managed prometheus addon
* `az aks create/update`: Block Azure Managed Grafana for managed prometheus addon in air gapped cloud
* `az aks create`: Correct use of "comma-separated" in help

### App Config

* `az appconfig feature filter update`: GA command
* `az appconfig kv export`: GA parameter `--export-as-reference`

### App Service

* `az functionapp create`: Add support for Node 20 for Flex function apps
* `az functionapp create`: Make Node 20 the default for node flex function apps and Python 3.11 the default for python flex function apps
* `az functionapp create`: Add support for SystemAssignedIdentity and UserAssignedIdentity as the deployment storage authentication type
* `az webapp update`: Add new parameter `--elastic-web-app-scale-limit` and scaling parameter options
* `az appservice plan update`: Add new parameter `--elastic-web-app-scale-limit` and scaling parameter options
* `az webapp deployment source config-zip`: Mark this command as deprecated, recommend using the `az webapp deploy` command instead of it

### ARM

* `az stack group create`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az stack group delete`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az stack sub create`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az stack sub delete`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az stack mg create`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az stack mg delete`: Deprecate the `--delete-resources`, `--delete-resource-groups` and `--delete-all` options and redirect to the new `--action-on-unmanage` argument
* `az deployment`: Treat nullable parameters as non-required for Bicep deployment

### ARO

* `az aro create/validate`: Fix bug in permissions validation that was preventing cluster creation in cases where the invoking user had the necessary permissions

### CDN

* `az afd profile`: Add parameter `--identity`

### Compute

* `az snapshot grant-access`: Add parameter `--file-format` to support specifying file format when making request for SAS on a VHDX file format snapshot
* `az vmss create`: Add `--enable-auto-os-upgrade` parameter to support automatic OS Upgrade while creating VMSS
* `az sig image-definition create`: Add warning message for Hyper-V generation and Security Type
* `az vmss create/update`: Add parameters to specify the security posture to be used for all virtual machines in the scale set
* `az capacity reservation group create/update`: Add new parameter `--sharing-profile` to support sharing capacity reservation group across subscriptions
* `az snapshot create`: Add parameter `--bandwidth-copy-speed` to allow a snapshot to be copied at a quicker speed

### DataBoxEdge

* `az databoxedge device`: Add command group `share` to support managing device share
* `az databoxedge device`: Add command group `user` to support managing device user
* `az databoxedge device`: Add command group `storage-account` to support managing device storage account
* `az databoxedge device`: Add command group `storage-account-credential` to support managing device storage account credential
* `az databoxedge device`: Add command `get-extended-information` to support getting extended information

### MySQL

* `az mysql flexible-server advanced-threat-protection-setting show`: Show server's advanced threat protection setting
* `az mysql flexible-server advanced-threat-protection-setting update`: Update server's advanced threat protection setting using `--state` as Enabled/Disabled
* `az mysql flexible-server import create`: Add support for online migration for single to flex

### NetAppFiles

* `az netappfiles check-file-path-availability`: Add new command to check if a file path is available
* `az netappfiles check-name-availability`: Add new command to check if a resource name is available
* `az netappfiles check-quota-availability`: Add new command to check if a quota is available
* `az netappfiles query-network-sibling-set`: Add new command to describe a network sibling set
* `az netappfiles update-network-sibling-set`: Add new command to update the network features of a network sibling set
* `az netappfiles quota-limit`: Add new command group to manage quota limits
* `az netappfiles volume populate-availability-zone`: Add new command to populate availability zone information for a volume
* `az netappfiles volume replication re-initialize`: Add new command to re-establish a previously deleted replication between 2 volumes that have a common ad-hoc or policy-based snapshots

### Network

* `az network virtual-appliance connection`: Add update command for NVA connection
* `az network dns record-set`: Add `--traffic-management-profile` for TMLink recordset feature
* `az network application-gateway waf-policy`: Change default rule set from CRS3.0 to DRS2.1
* `az network virtual-appliance`: Add `--internet-ingress-ips` and `--network-profile`
