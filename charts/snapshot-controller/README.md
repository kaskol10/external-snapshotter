# snapshot-controller

![Version: 4.2.1](https://img.shields.io/badge/Version-4.2.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 4.2.1](https://img.shields.io/badge/AppVersion-4.2.1-informational?style=flat-square)

A Helm chart for Kubernetes

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| kaskol10 |  | https://github.com/kaskol10 |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` | Node Affinity and inter-pod affinity/anti-affinity |
| args | list | `["--v=5","--leader-election=true","--http-endpoint=:8080"]` | Possible arguments can be found in the [Snapshot Controller command-line options](https://github.com/kubernetes-csi/external-snapshotter#snapshot-controller-command-line-options) |
| autoscaling.enabled | bool | `false` |  |
| autoscaling.maxReplicas | int | `100` | HPA Max Replicas |
| autoscaling.minReplicas | int | `1` |  |
| autoscaling.targetCPUUtilizationPercentage | int | `80` |  |
| fullnameOverride | string | `""` | Full name override |
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy strategy when the kubelet attempts to pull(download) the specified image |
| image.repository | string | `"gcr.io/k8s-staging-sig-storage/snapshot-controller"` | Image to use for deploying |
| image.tag | string | `"v5.0.0-rc1"` | Overrides the image tag whose default is the chart appVersion. |
| imagePullSecrets | list | `[]` | Add image pull secrets if requires |
| minReadySeconds | int | `15` | The snapshot controller won't be marked as ready if the v1 CRDs are unavailable in [#504](https://github.com/kubernetes-csi/external-snapshotter/pull/504) the snapshot-controller will exit after around 7.5 seconds if it can't find the v1 CRDs so this value should be greater than that |
| nameOverride | string | `""` | Naming override |
| nodeSelector | object | `{}` | Node selection constraint  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| rbac.create | bool | `true` | Create all the RBAC resources needed |
| replicaCount | int | `2` | Number of replicas in the deployment |
| resources | object | `{}` |  |
| rollingUpdate | object | `{"enabled":true,"maxSurge":0,"maxUnavailable":1}` | Rolling update configuration |
| rollingUpdate.enabled | bool | `true` | Enable/disable rolling updates (default: true) |
| rollingUpdate.maxSurge | int | `0` | Max number of pods that can be created above the desired number of replicas |
| securityContext | object | `{}` |  |
| service.port | int | `8080` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | Annotations to add to the service account |
| serviceAccount.create | bool | `true` | Specifies whether a service account should be created |
| serviceAccount.name | string | `""` | The name of the service account to use. If not set and create is true, a name is generated using the fullname template |
| tolerations | list | `[]` | Allow the pods to schedule onto nodes with matching taints |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.5.0](https://github.com/norwoodj/helm-docs/releases/v1.5.0)
