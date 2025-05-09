# Storage Account

Create or update a Storage Account.

## Parameters

Parameter name | Required | Type | Description
-------------- | -------- | ---- | -----------
name           | Yes      | string | The name of the storage account.
location       | No       | string | The location of the storage account.

### name

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the storage account.

### location

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The location of the storage account.

**Default value**

```text
[resourceGroup().location]
```

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
        "name": {
            "value": ""
        }
    }
}
```
