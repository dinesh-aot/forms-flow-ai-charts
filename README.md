# FormsFlow.ai

[FormsFlow.ai](https://formsflow.ai/) formsflow.ai is a completely free and open source framework that integrates intelligent forms, decision making workflows, and powerful analytics.

This chart installs the forms-flow microservices needed for deploying formsflow.ai.

## Get Repo Info

```console
helm repo add formsflow https://aot-technologies.github.io/forms-flow-ai-charts
helm repo update
```

_See [helm repo](https://helm.sh/docs/helm/helm_repo/) for command documentation._

##E.g Install Component Chart
```console
# Helm 3
$ helm install [RELEASE_NAME] formsflow/[COMPONENT_NAME] [flags]
```


## Install Formsflow.ai
```console
# Helm 3

helm install forms-flow-ai formsflow/forms-flow-ai \
	--set Domain=$DOMAIN_NAME \ 
	--set forms-flow-idm.keycloak.ingress.hostname=forms-flow-idm-$NAMESPACE.$DOMAIN_NAME \
	--namespace $NAMESPACE
 
helm install forms-flow-analytics formsflow/forms-flow-analytics \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-forms formsflow/forms-flow-forms \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-idm formsflow/forms-flow-idm \
	--set Domain=$DOMAIN_NAME \
	--set keycloak.ingress.hostname=forms-flow-idm-$NAMESPACE.$DOMAIN_NAME \
	--namespace $NAMESPACE 

helm install forms-flow-admin formsflow/forms-flow-admin \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-api formsflow/forms-flow-api \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-bpm formsflow/forms-flow-bpm \
	--set Domain=$DOMAIN_NAME \
	--set camunda.websocket.securityOrigin=https://*.$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-data-analysis formsflow/forms-flow-data-analysis \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-web formsflow/forms-flow-web \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

helm install forms-flow-documents-api formsflow/forms-flow-documents-api \
	--set Domain=$DOMAIN_NAME \
	--namespace $NAMESPACE

```
## Uninstall Chart

```console
# Helm 3
$ helm uninstall [RELEASE_NAME]

helm uninstall forms-flow-admin -n $NAMESPACE

helm uninstall forms-flow-ai -n $NAMESPACE

helm uninstall forms-flow-api -n $NAMESPACE

helm uninstall forms-flow-analytics -n $NAMESPACE

helm uninstall forms-flow-bpm -n $NAMESPACE

helm uninstall forms-flow-data-analysis -n $NAMESPACE

helm uninstall forms-flow-forms -n $NAMESPACE

helm uninstall forms-flow-idm -n $NAMESPACE

helm uninstall forms-flow-web -n $NAMESPACE

helm uninstall forms-flow-documents-api -n $NAMESPACE

```

This removes all the Kubernetes components associated with the chart and deletes the release.

Note: Kubernetes Persistent Volumes Claims are not deleted using the helm uninstall command.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## Upgrade Chart

```console
# Helm 3
$ helm upgrade [RELEASE_NAME] forms-flow-ai/forms-flow-ai [flags]
```

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

Visit the chart's [CHANGELOG](./CHANGELOG.md) to view the chart's release history.
For migration between major version check [migration guide](#migration-guide).

## Configuration

See [Customizing the Chart Before Installing](https://helm.sh/docs/intro/using_helm/#customizing-the-chart-before-installing).
To see all configurable options with detailed comments, visit the chart's [values.yaml](./values.yaml), or run these configuration commands:

```console
# Helm 3
$ helm show values forms-flow-ai/forms-flow-ai
```

#For a summary of all configurable options, see [VALUES_SUMMARY.md](./VALUES_SUMMARY.md)
