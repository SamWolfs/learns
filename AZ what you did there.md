## Key Vault

### Create

```sh
RESOURCE_GROUP_NAME="my-resource-group"
KV_NAME="my-keyvault"
LOCATION="usgovvirginia"
az keyvault create --resource-group "$RESOURCE_GROUP_NAME" --name "$KV_NAME" --location "$LOCATION"
```

## App

### Create

```sh
APP="APP_NAME"
REDIRECT_URI="https://redirect.me"
OTHER_REDIRECT_URI="https://redirect.me"
az ad app create --display-name "$APP" \
    --web-redirect-uris "$REDIRECT_URI" "$OTHER_REDIRECT_URI"
```

## Service Principal

### Create

```sh
APP="APP_NAME"
APP_ID=$(az ad app list --display-name "$APP" | jq -r '.[].appId')
az ad sp create --id "$APP_ID"
```

### Generate Credential

```sh
APP="APP_NAME"
DESCRIPTION="Secret"
APP_ID=$(az ad app list --display-name "$APP" | jq -r '.[].appId')
az ad app credential reset --id "$APP_ID" --display-name "$DESCRIPTION" --append
```
