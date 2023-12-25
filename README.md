# Sentiment Analysis Service Helm Chart

This Helm chart deploys the Sentiment Analysis Service on a Kubernetes cluster using the Helm package manager. The repo for the service can be [found here](https://github.com/GizzmoAsus/sentiment-analysis-service)

## Prerequisites

- Kubernetes 1.12+
- Helm 3.0+

## Installing the Chart

To install the chart with the release name `my-release`:

```bash
helm install my-release <path-to-chart>
```

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```bash
helm delete my-release
```

## Configuration

The following table lists the configurable parameters of the Sentiment Analysis Service chart and their default values.

| Parameter                | Description                                      | Default                      |
| ------------------------ | ------------------------------------------------ | ---------------------------- |
| `replicaCount`           | Number of replicas                               | `1`                          |
| `image.repository`       | Image repository                                 | `<your-image-repository>`    |
| `image.pullPolicy`       | Image pull policy                                | `IfNotPresent`               |
| `image.tag`              | Image tag                                        | `<tag-version>`              |
| `imagePullSecrets`       | Image pull secrets                               | `""`                         |
| `nameOverride`           | Override the name of the chart                   | `""`                         |
| `fullnameOverride`       | Override the fullname of the chart               | `""`                         |
| `securityContext`        | Security context for the pod                     | `{}`                         |
| `service.type`           | Kubernetes Service type                          | `ClusterIP`                  |
| `service.port`           | Service HTTP port                                | `8080`                       |
| `ingress.enabled`        | Enable ingress controller resource               | `true`                       |
| `ingress.className`      | Ingress class name                               | `<ingress-class-name>`       |
| `ingress.annotations`    | Ingress annotations                              | `{}`                         |
| `ingress.hosts`          | Hosts and paths for ingress                      | `[{"host": "example.com"}]`  |
| `ingress.tls`            | Ingress TLS configuration                        | `[]`                         |

## Usage

After installing the chart, the Sentiment Analysis Service will be deployed to your Kubernetes cluster. You can interact with the service via its REST API.

### Analyzing Sentiments

- **Endpoint**: `POST /`
- **Payload**:

```json
{
  "text": "string"
}
```

## Customizing the Chart

To modify the default configuration, create a `values.yaml` file with your settings and install/upgrade the chart using:

```bash
helm install my-release <path-to-chart> -f values.yaml
```

## Contributing

If you have suggestions for improving the chart, please open an issue or pull request in the repository.

## License

This Helm chart is distributed under the MIT License. See [LICENSE](LICENSE) for more information.

```
NOTE: Remember to replace placeholders like `<path-to-chart>`, `<your-image-repository>`, `<tag-version>`, and `<ingress-class-name>` with the actual values relevant to your chart.
```
