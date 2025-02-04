# cloudsql-proxy

The Cloud SQL Proxy provides secure access to your Cloud SQL Postgres/MySQL instances without having to whitelist IP addresses or configure SSL

![Version: 1.0.0](https://img.shields.io/badge/Version-1.0.0-informational?style=flat-square) ![AppVersion: 2.14.2](https://img.shields.io/badge/AppVersion-2.14.2-informational?style=flat-square)

## Install

To install the chart use the following command:

```bash
helm upgrade --install <release_name> . -f <your_custom_values.yam>
```

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| image.pullPolicy | string | `"IfNotPresent"` | Image pull policy |
| image.registry | string | `"eu.gcr.io/cloud-sql-connectors/cloud-sql-proxy"` | Docker registry and image name |
| image.tag | string | `""` | By default, it uses `.Chart.AppVersion` if the value is not set. |
| instanceConnectionName | string | `""` | To find your Cloud SQL instance's connection name, visit the detail page of your Cloud SQL instance in the console |
| port | int | `3306` | The port that the proxy should open to listen for database connections from the application. MySQL: `3306`, PostgreSQL: `5432` |
| serviceAccount.automountToken | string | `"false"` | Automount service account token to give the application access to the Kubernetes API |
| serviceAccount.create | bool | `true` | Create a service account for the proxy |
| serviceAccount.name | string | `"cloud-sql-proxy"` | Service account name |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.14.2](https://github.com/norwoodj/helm-docs/releases/v1.14.2)
