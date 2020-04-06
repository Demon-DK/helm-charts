# Helm Chart for Adminer

[![License](https://img.shields.io/badge/License-Apache%202.0-blue.svg)](https://opensource.org/licenses/Apache-2.0) 

## Introduction
This [Helm](https://github.com/kubernetes/helm) chart installs [Adminer](https://www.adminer.org) in a Kubernetes cluster.

## Prerequisites
- Helm 3+
- Kubernetes cluster 1.10+


## Installation

### Add Helm repository
  ```bash
  helm repo add demon https://demon-dk.github.io/helm-charts
  helm repo update
  ```

### Install the chart
  ```bash
  helm install --generate-name demon/adminer 
  or
  helm install [your-release-name] demon/adminer
  ```

## Uninstallation
To uninstall/delete the deployment:
```bash
helm delete [your-release-name]
```

## Configuration

The following table lists the configurable parameters of the Adminer chart and the default values.

| Parameter                         | Description                                                             | Default                     |
| --------------------------------- | ----------------------------------------------------------------------- | --------------------------- |
| **Image**                                                                                                                                 |
| `image.repository`                | Image                                                                   | `adminer`                   |
| `image.tag`                       | Image tag                                                               | `4.7.6-standalone`          |
| `image.pullPolicy`                | Image pull policy                                                       | `Always`              |
| **ConfigMap**                                                                                                                                |
| `configmap.ADMINER_DESIGN`        | List of plugins to install. You can find the list of plugins on [GitHub](https://github.com/vrana/adminer/tree/master/plugins)| `pepa-linha`|
| `configmap.ADMINER_PLUGINS`       | A bundled design to use. You can find the list of designs on [GitHub](https://github.com/vrana/adminer/tree/master/designs)| `tables-filter`|
| `configmap.ADMINER_DEFAULT_SERVER`| The default host                                                        | `""`                          |
| **Command**                                                                                                                               |
| `commands`                        | Container entrypoint commands                                           | `[]`                        |
| **Service**                                                                                                                               |
| `service.type`                    | Service type                                                            | `ClusterIP`                 |
| `service.port`                    | The service port                                                        | `8080`                        |
| `service.annotations`             | Custom annotations for service                                          | `[]`                        |
| `service.cluster_ip`              | Service type                                                            | `{}`                 |
| `service.external_ips`            | Service type                                                            | `[]`                 |
| **Ingress**                                                                                                                               |
| `ingress.enabled`                 | Enables Ingress                                                         | `false`                     |
| `ingress.annotations`             | Ingress annotations                                                     | `{}`                        |
| `ingress.labels`                  | Custom labels                                                           | `{}`                        |
| `ingress.hosts`                   | Ingress accepted hostnames                                              | `[]`                        |
| `ingress.tls`                     | Ingress TLS configuration                                               | `[]`                        |
| **Resources**                                                                                                                             |
| `resources.requests.cpu`          |  CPU requests                                                           |  `50m`   |
| `resources.requests.memory`       |  Memory requests                                                        |  `128Mi`   |
| `resources.limits.cpu`            |  CPU limits                                                             |  `400m`   |
| `resources.limits.memory`         |  Memory limits                                                          |  `512Mi`   |
| **Tolerations**                                                                                                                           |
| `tolerations`                     | Add tolerations                                                         | `[]`                        |
| **Affinity**                                                                                                                              |
| `affinity`                        | node/pod affinities                                                     | `{}`                        |
| **LivenessProbe**                                                                                                                         |
| `livenessProbe`                   | Liveness probe settings                                                 | `{}`                        |
| **ReadnessProbe**                                                                                                                         |
| `readinessProbe`                  | Readiness probe settings                                                | `{}`                        |

## Credits

Initially inspired from https://github.com/mogaal/helm-charts/tree/master/adminer.


## License

[Apache License 2.0](/LICENSE.md)

