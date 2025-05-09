# Key Vault

Create or update a Key Vault.

## Parameters

Parameter name | Required | Type | Description
-------------- | -------- | ---- | -----------
vaultName      | Yes      | string | The name of the Key Vault.
location       | No       | string | The Azure region to deploy to.
accessPolicies | No       | array | The access policies defined for this vault.
useDeployment  | No       | bool | Determines if Azure can deploy certificates from this Key Vault.
useTemplate    | No       | bool | Determines if templates can reference secrets from this Key Vault.
useDiskEncryption | No       | bool | Determines if this Key Vault can be used for Azure Disk Encryption.
useSoftDelete  | No       | bool | Determine if soft delete is enabled on this Key Vault.
usePurgeProtection | No       | bool | Determine if purge protection is enabled on this Key Vault.
networkAcls    | No       | object | The network firewall defined for this vault.
workspaceId    | No       | string | The workspace to store audit logs.
tags           | Yes      | object | Tags to apply to the resource.

### vaultName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the Key Vault.

### location

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The Azure region to deploy to.

**Default value**

```text
[resourceGroup().location]
```

### accessPolicies

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The access policies defined for this vault.

### useDeployment

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Determines if Azure can deploy certificates from this Key Vault.

**Default value**

```text
False
```

### useTemplate

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Determines if templates can reference secrets from this Key Vault.

**Default value**

```text
False
```

### useDiskEncryption

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Determines if this Key Vault can be used for Azure Disk Encryption.

**Default value**

```text
False
```

### useSoftDelete

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Determine if soft delete is enabled on this Key Vault.

**Default value**

```text
True
```

### usePurgeProtection

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

Determine if purge protection is enabled on this Key Vault.

**Default value**

```text
True
```

### networkAcls

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The network firewall defined for this vault.

**Default value**

```json
{
    "defaultAction": "Allow",
    "bypass": "AzureServices",
    "ipRules": [],
    "virtualNetworkRules": []
}
```

### workspaceId

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The workspace to store audit logs.

### tags

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Tags to apply to the resource.

## Outputs

Name | Type | Description
---- | ---- | -----------
resourceId | string | A unique resource identifier for the Key Vault.

## Snippets

### Parameter file

```json
{
    "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentParameters.json#",
    "contentVersion": "1.0.0.0",
    "metadata": {
        "template": null
    },
    "parameters": {
        "vaultName": {
            "value": "<name>"
        },
        "accessPolicies": {
            "value": [
                {
                    "objectId": "<object_id>",
                    "tenantId": "<tenant_id>",
                    "permissions": {
                        "secrets": [
                            "Get",
                            "List",
                            "Set"
                        ]
                    }
                }
            ]
        },
        "useDeployment": {
            "value": false
        },
        "useTemplate": {
            "value": false
        },
        "useDiskEncryption": {
            "value": false
        },
        "networkAcls": {
            "value": {
                "defaultAction": "Allow",
                "bypass": "AzureServices",
                "ipRules": [],
                "virtualNetworkRules": []
            }
        },
        "workspaceId": {
            "value": "<resource_id>"
        },
        "tags": {
            "value": {
                "service": "<service_name>",
                "env": "prod"
            }
        }
    }
}
```
