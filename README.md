# alertmanager-webhook-servicenow
## Description

## Values
| Key | Default | Description |
| --- | ------- | ----------- |
| replicaCount | `1` | Number of replicas |
| image.repository | `'fxinnovation/awsn'` | Repository of the docker image to be used |
| image.tag | `'0.2.0'` | Tag of the docker image to be used |
| image.pullPolicy | `'IfNotPresent'` | Pull policy of the image to be used |
| nameOverride | `''` | overrides the name of the chart |
| fullnameOverride | `''` | overrides the full name of the chart |
| service.type | `'ClusterIP'` | Type of service to be used |
| service.port | `80` | Service port to be used |
| resources.limits.cpu | `50m` | Limit CPU of the container |
| resources.limits.memory | `128Mi` | Memory limit of the container |
| resources.requests.cpu | `10m` | Requested CPU of the container |
| resources.requests.memory | `32Mi` | Memory requested by the container |
| nodeSelector | `{}` | node selection constraint |
| tolerations | `[]` | scheduling tolerations |
| affinity | `{}` | node and inter-pod affinity and ainti-affinity |
| configuration | see values.yaml | webhook configuration, except `service_now` section |
| credentials_servicenow | `'name-of-the-seret'` | Name of the kubernetes secret with ServiceNow credentials |

### credentials_servicenow
Example Secret:
```yaml
---
kind: Secret
apiVersion: v1
metadata:
  name: '<name of the secret>'
type: Opaque
data:
  instance_name: '<base64 value>'
  passwrod: '<base64 value>'
  username: '<base64 value>'
```
