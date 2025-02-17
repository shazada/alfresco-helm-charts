# alfresco-share

![Version: 0.3.0](https://img.shields.io/badge/Version-0.3.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 23.1.1](https://img.shields.io/badge/AppVersion-23.1.1-informational?style=flat-square)

Alfresco Share Helm chart for Kubernetes

Checkout [alfresco-content-services chart's doc](https://github.com/Alfresco/acs-deployment/blob/master/docs/helm/README.md) for an example of how to leverage this chart from an umbrella chart.

## Requirements

| Repository | Name | Version |
|------------|------|---------|
| https://alfresco.github.io/alfresco-helm-charts | alfresco-common | 3.1.0 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | string | `""` | string representation of the YAML affinity rules (can use templates) |
| args | list | `[]` |  |
| command | list | `[]` |  |
| environment.CATALINA_OPTS | string | `"-XX:MinRAMPercentage=50 -XX:MaxRAMPercentage=80"` |  |
| extraInitContainers | list | `[]` |  |
| extraSideContainers | list | `[]` |  |
| extraVolumeMounts | list | `[]` |  |
| extraVolumes | list | `[]` |  |
| fullnameOverride | string | `""` | Define a fully static name |
| global.alfrescoRegistryPullSecrets | string | `"quay-registry-secret"` | If a private image registry a secret can be defined and passed to kubernetes, see: https://github.com/Alfresco/acs-deployment/blob/a924ad6670911f64f1bba680682d266dd4ea27fb/docs/helm/eks-deployment.md#docker-registry-secret |
| global.known_urls | string | `nil` | a fallback for .Values.known_urls that can be shared between charts |
| image.port | int | `8080` | Internal port where the pod is listening. Should only be changed is you use a custom image which uses a different port. |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"quay.io/alfresco/alfresco-share"` |  |
| image.tag | string | `"23.1.1"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/affinity" | string | `"cookie"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/proxy-body-size" | string | `"5g"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/session-cookie-expires" | string | `"604800"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/session-cookie-max-age" | string | `"604800"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/session-cookie-name" | string | `"alfrescoShare"` |  |
| ingress.annotations."nginx.ingress.kubernetes.io/session-cookie-path" | string | `"/share"` |  |
| ingress.enabled | bool | `true` |  |
| ingress.hosts[0].paths[0].path | string | `"/share"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| known_urls | string | `nil` | Provide the list of URL considered allowed to access Share resources (used for CSRF protection). The value be either a list of strings or a single string separated by spaces. |
| livenessProbe.initialDelaySeconds | int | `15` |  |
| livenessProbe.periodSeconds | int | `20` |  |
| livenessProbe.timeoutSeconds | int | `5` |  |
| nameOverride | string | `""` | Define a partially static name |
| nodeSelector | object | `{}` |  |
| podAnnotations | object | `{}` |  |
| podLabels | object | `{}` |  |
| podSecurityContext.runAsNonRoot | bool | `true` |  |
| readinessProbe.initialDelaySeconds | int | `15` |  |
| readinessProbe.periodSeconds | int | `30` |  |
| readinessProbe.timeoutSeconds | int | `5` |  |
| repository.existingConfigMap.keys.host | string | `"REPO_HOST"` | name of the key in the configMap where to find the repository service host |
| repository.existingConfigMap.keys.port | string | `"REPO_PORT"` | name of the key in the configMap where to find the repository service port |
| repository.existingConfigMap.name | string | `nil` | a pre-existing configmap which provides expected configuration for Share |
| repository.host | string | `"localhost"` | repository hostname/servicename |
| repository.port | int | `8080` | repository port where service is exposed |
| resources.limits.cpu | string | `"4"` |  |
| resources.limits.memory | string | `"2000Mi"` |  |
| resources.requests.cpu | string | `"250m"` |  |
| resources.requests.memory | string | `"512Mi"` |  |
| securityContext.capabilities.drop[0] | string | `"NET_RAW"` |  |
| securityContext.capabilities.drop[1] | string | `"ALL"` |  |
| securityContext.runAsNonRoot | bool | `false` |  |
| service.name | string | `"share"` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `"share-sa"` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| strategy.rollingUpdate.maxSurge | int | `1` |  |
| strategy.rollingUpdate.maxUnavailable | int | `0` |  |
| strategy.type | string | `"RollingUpdate"` |  |
| tolerations | list | `[]` |  |
