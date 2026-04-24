# ocsinventory

![Version: 0.1.0](https://img.shields.io/badge/Version-0.1.0-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.12.4](https://img.shields.io/badge/AppVersion-2.12.4-informational?style=flat-square)

Open Computers and Software Inventory Next Generation is an assets management and deployment solution.

**Homepage:** <https://ocsinventory-ng.org/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Stephane Malinet | <s.malinet@monaco-telecom.mc> | <https://github.com/smalinet> |

## Source Code

* <http://wiki.ocsinventory-ng.org>
* <https://github.com/OCSInventory-NG/OCSInventory-Docker-Image>

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity |
| database | object | `{"create":false,"database":"","hostname":"","jobName":"createdb","password":"","root_password":"","username":""}` | Configuration for creating a database on an existing server |
| deployment.annotations | object | `{}` | Deployment annotations |
| deployment.labels | object | `{}` | Deployment labels |
| deployment.replicaCount | int | `1` |  |
| dnsConfig | object | `{}` | DNS config |
| dnsPolicy | string | `"ClusterFirst"` | DNS policy |
| externalDatabase | object | `{"database":"","enabled":false,"hostname":"","password":"","username":""}` | External database configuration |
| extraEnv | list | `[]` | Extra nvironment |
| extraVolumeMounts | list | `[]` | Extra volume mounts |
| extraVolumes | list | `[]` | Extra volumes |
| fullnameOverride | string | `""` |  |
| image | object | `{"pullPolicy":"IfNotPresent","registry":"docker.io","repository":"ocsinventory/ocsinventory-docker-image","tag":""}` | Official OCS Inventory image version https://hub.docker.com/r/ocsinventory/ocsinventory-docker-image |
| image.pullPolicy | string | `"IfNotPresent"` | Image pullPolicy |
| image.registry | string | `"docker.io"` | Image registry |
| image.repository | string | `"ocsinventory/ocsinventory-docker-image"` | Image repository |
| image.tag | string | `""` | Image specific tag |
| imagePullSecrets | list | `[]` | Image pull secrets |
| ingress | object | `{"annotations":{"cert-manager.io/cluster-issuer":"","kubernetes.io/ingress.class":"nginx","nginx.ingress.kubernetes.io/app-root":"/ocsreports/","nginx.ingress.kubernetes.io/force-ssl-redirect":"true","nginx.ingress.kubernetes.io/proxy-body-size":"200M","nginx.ingress.kubernetes.io/proxy-connect-timeout":"300s","nginx.ingress.kubernetes.io/proxy-read-timeout":"300s","nginx.ingress.kubernetes.io/proxy-send-timeout":"300s"},"basicauth":{"authRealm":"Authentication Required","enabled":false,"password":"","paths":["/ocsapi","/ocsinventory"],"username":""},"enabled":true,"hosts":["ocsng.example.com"],"labels":{},"tls":true}` | Allowing use of ingress controllers https://kubernetes.io/docs/concepts/services-networking/ingress/ |
| ingress.enabled | bool | `true` | Ingress enabled |
| ingress.labels | object | `{}` | Ingress labels |
| initContainers | list | `[]` | InitContainers |
| metrics.enabled | bool | `false` | Metrics enabled |
| metrics.image.pullPolicy | string | `"IfNotPresent"` |  |
| metrics.image.registry | string | `"docker.io"` |  |
| metrics.image.repository | string | `"bitnami/apache-exporter"` |  |
| metrics.image.tag | string | `"1.0.3-debian-11-r2"` |  |
| metrics.resources | object | `{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"100m","memory":"100Mi"}}` | Metrics ressources |
| metrics.serviceMonitor.enabled | bool | `false` |  |
| metrics.serviceMonitor.labels | object | `{"prometheus":"prometheus","release":"tobedefined"}` | Metrics serviceMonitor labels |
| nameOverride | string | `""` |  |
| nodeSelector | object | `{}` | Node selector labels |
| persistence | object | `{"accessMode":"ReadWriteOnce","annotations":{},"enabled":false,"size":"10Gi","storageClass":""}` | Enable persistence using Persistent Volume Claims https://kubernetes.io/docs/concepts/storage/persistent-volumes/  |
| persistence.accessMode | string | `"ReadWriteOnce"` | PersistentVolumeClaim accessMode |
| persistence.annotations | object | `{}` | PersistentVolumeClaim annotations |
| persistence.enabled | bool | `false` | Persistence enabled |
| persistence.size | string | `"10Gi"` | PersistentVolumeClaim size |
| persistence.storageClass | string | `""` | Set storage class here |
| phpconfig | object | `{"ocsinventory":"upload_max_filesize = 200M\npost_max_size = 201M\nmax_execution_time = -1\nmax_input_time = -1\n"}` | PHP configuration https://www.php.net/manual/ini.core.php |
| podAnnotations | object | `{}` | Pod annotations |
| podAnnotations | object | `{}` | Pod annotations |
| podSecurityContext | object | `{}` | Pod security context |
| resources | object | `{"limits":{"cpu":"200m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}}` | Ressources limits and requests for the container https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/ |
| securityContext | object | `{}` | Security context |
| tolerations | list | `[]` | Tolerations |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
