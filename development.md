# Development

Quick start a Service Bus environment:

```sh
az group create -n "{rg}" -l "eastus2"
az servicebus namespace create -n "{bus}" -g "{rg}" -l "eastus2"
az servicebus queue create -n "queue1" --namespace-name "{bus}" -g "{rg}" --enable-partitioning

az servicebus namespace authorization-rule keys list \
  -g "{rg}" \
  --namespace-name "{bus}" \
  --name "RootManageSharedAccessKey" \
  --query "primaryConnectionString" -o tsv
```
