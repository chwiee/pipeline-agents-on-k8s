# Pipelines Agents on Kubernetes

## What i need

[x] Docker >= 20.0.0 | Buildah
[x] Cluster EKS

## Cluster Reqs

Precisamos ter as secrets abaixo (ajuste os valores para o seu ambiente):
````
k create secret generic azuredevops-secrets \
    --from-literal=AZP_URL=https://dev.azure.com/ORG
    --from-literal=AZP_TOKEN=
    --from-literal=AZP_POOL=
    --from-literal=ENVIRONMENT=
    --from-literal=OWNER=
    --from-literal=DEPLOY_TYPE=
````

ENVIRONMENT     -> Define o ambiente em que o Agent está rodando
OWNER           -> Nome do responsável pelo Agent (pessoa ou time)
DEPLOY_TYPE     -> Tipo de Deploy que será aceito BUILD, DEPLOY, HELM

## KEDA?

Sim podemos ter um Agent com KEDA onde ele ficará zerado no Cluster e apenas se for triggado o mesmo vai iniciar :) 

Caso queira aplique o manifest-keda se preferir ter 1 agent unico com scale manual use o manifest 

# TKS

Wallace Bruno Gentil (Chwiee.)