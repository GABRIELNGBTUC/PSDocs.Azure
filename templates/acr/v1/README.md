# Container Registry

Create or update a Container Registry.

## Parameters

Parameter name | Required | Type | Description
-------------- | -------- | ---- | -----------
registryName   | Yes      | string | The name of the container registry.
location       | No       | string | The location to deploy the container registry.
registrySku    | No       | string | The container registry SKU.
tags           | Yes      | object | Tags to apply to the resource.

### registryName

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

The name of the container registry.

### location

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The location to deploy the container registry.

**Default value**

```text
[resourceGroup().location]
```

### registrySku

![Parameter Setting](https://img.shields.io/badge/parameter-optional-green?style=flat-square)

The container registry SKU.

**Default value**

```text
Basic
```

**Allowed values**

```text
Basic
Standard
Premium
```

### tags

![Parameter Setting](https://img.shields.io/badge/parameter-required-orange?style=flat-square)

Tags to apply to the resource.

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
        "registryName": {
            "value": "<name>"
        },
        "registrySku": {
            "value": "Basic"
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
