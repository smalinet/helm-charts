# ocsinventory

![Version: 0.3.2](https://img.shields.io/badge/Version-0.3.2-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 2.12.4](https://img.shields.io/badge/AppVersion-2.12.4-informational?style=flat-square)

Open Computers and Software Inventory Next Generation is an assets management and deployment solution.

**Homepage:** <https://ocsinventory-ng.org/>

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| Stephane Malinet | <s.malinet@monaco-telecom.mc> | <https://github.com/smalinet> |

## Source Code

* <https://wiki.ocsinventory-ng.org>
* <https://github.com/OCSInventory-NG/OCSInventory-Docker-Image>

## Usage

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

```sh
helm repo add smalinet https://smalinet.github.io/helm-charts
```

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages. You can then run `helm search repo
smalinet` to see the charts.

To install the ocsinventory chart:

```sh
helm upgrade --install ocsinventory smalinet/ocsinventory
```

To install the ocsinventory chart (using an OCI-based registry):

```sh
helm upgrade --install ocsinventory oci://ghcr.io/smalinet/helm-charts/ocsinventory:<tag>
 ```

To uninstall the chart:

```sh
helm delete ocsinventory
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Affinity |
| database | object | `{"create":false,"database":"","existingSecret":"","hostname":"","password":"","root_password":"","username":""}` | Configuration for the database on an existing server |
| database.create | bool | `false` | If true, you must supply the password for the user root |
| database.database | string | `""` | Database name. db-name in the secret |
| database.existingSecret | string | `""` | The name for an existing secret. Please refer to templates/secrets.yaml for the minimal content. |
| database.hostname | string | `""` | Database hostname. db-host in the secret |
| database.password | string | `""` | Database password. db-password in the secret |
| database.root_password | string | `""` | The password for the user root - root-pass in the secret |
| database.username | string | `""` | Database username. db-user in the secret |
| deployment.annotations | object | `{}` | Deployment annotations |
| deployment.labels | object | `{}` | Deployment labels |
| deployment.replicaCount | int | `1` | Number of replicas to be deployed |
| dnsConfig | object | `{}` | DNS config |
| dnsPolicy | string | `"ClusterFirst"` | DNS policy |
| extraEnv | list | `[]` | Extra environment |
| extraVolumeMounts | list | `[]` | Extra volume mounts |
| extraVolumes | list | `[]` | Extra volumes |
| fullnameOverride | string | `""` | Override the full name of the application |
| image | object | `{"pullPolicy":"IfNotPresent","registry":"docker.io","repository":"ocsinventory/ocsinventory-docker-image","tag":""}` | Official OCS Inventory image version https://hub.docker.com/r/ocsinventory/ocsinventory-docker-image |
| image.pullPolicy | string | `"IfNotPresent"` | Image pullPolicy |
| image.registry | string | `"docker.io"` | Image registry |
| image.repository | string | `"ocsinventory/ocsinventory-docker-image"` | Image repository |
| image.tag | string | `""` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Image pull secrets |
| ingress | object | `{"annotations":{},"basicauth":{"authRealm":"Authentication Required","enabled":false,"password":"","paths":["/ocsapi","/ocsinventory"],"username":""},"className":"","enabled":false,"hosts":["ocsng.example.com"],"labels":{},"tls":true}` | Allowing use of ingress controllers https://kubernetes.io/docs/concepts/services-networking/ingress/ |
| ingress.className | string | `""` | Ingress className |
| ingress.enabled | bool | `false` | Ingress enabled |
| ingress.labels | object | `{}` | Ingress labels |
| initContainers | list | `[]` | InitContainers |
| metrics.enabled | bool | `false` | Metrics enabled |
| metrics.image.pullPolicy | string | `"IfNotPresent"` | Metrics image pullPolicy |
| metrics.image.registry | string | `"docker.io"` | Metrics image registry |
| metrics.image.repository | string | `"bitnami/apache-exporter"` | Metrics image repository |
| metrics.image.tag | string | `"1.0.3-debian-11-r2"` | Metrics image tag |
| metrics.resources | object | `{"limits":{"cpu":"200m","memory":"256Mi"},"requests":{"cpu":"100m","memory":"100Mi"}}` | Metrics ressources |
| metrics.serviceMonitor.enabled | bool | `false` | Metrics serviceMonitor enabled |
| metrics.serviceMonitor.labels | object | `{"prometheus":"prometheus","release":"tobedefined"}` | Metrics serviceMonitor labels |
| nameOverride | string | `""` | Override the name of the application |
| nodeSelector | object | `{}` | Node selector labels |
| persistence | object | `{"accessMode":["ReadWriteOnce"],"annotations":{},"enabled":false,"size":"1Gi","storageClass":""}` | Enable persistence using Persistent Volume Claims https://kubernetes.io/docs/concepts/storage/persistent-volumes/ |
| persistence.accessMode | list | `["ReadWriteOnce"]` | PersistentVolumeClaim accessMode |
| persistence.annotations | object | `{}` | PersistentVolumeClaim annotations |
| persistence.enabled | bool | `false` | Persistence enabled |
| persistence.size | string | `"1Gi"` | PersistentVolumeClaim size. If persistence=false the size is used by an emptyDir |
| persistence.storageClass | string | `""` | Set storage class here |
| phpconfig | object | `{"ocsinventory":"upload_max_filesize = 200M\npost_max_size = 201M\nmax_execution_time = -1\nmax_input_time = -1\n"}` | PHP configuration https://www.php.net/manual/ini.core.php |
| podAnnotations | object | `{}` | Pod annotations |
| podSecurityContext | object | `{}` | Pod security context |
| resources | object | `{"limits":{"cpu":"200m","memory":"512Mi"},"requests":{"cpu":"100m","memory":"256Mi"}}` | Ressources limits and requests for the container https://kubernetes.io/docs/concepts/configuration/manage-resources-containers/ |
| securityContext | object | `{}` | Security context |
| service.annotations | object | `{}` | Service annotations |
| service.ipFamilies | list | `["IPv4"]` | Service ipFamilies |
| service.ipFamilyPolicy | string | `"SingleStack"` | Service ipFamilyPolicy SingleStack|PreferDualStack|RequireDualStack |
| service.type | string | `"ClusterIP"` | Service type |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.automount | bool | `false` | Automatically mount the service account token |
| serviceAccount.create | bool | `false` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` | Tolerations |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
