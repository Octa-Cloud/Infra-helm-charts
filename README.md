# Helm Charts Repository

This repository contains Helm charts for the KEA project microservices.

## Charts

- **user-service**: User management microservice

## Usage

### Add this repository to Helm

```bash
helm repo add kea-charts https://github.com/Octa-Cloud/helm-charts
helm repo update
```

### Install a chart

```bash
helm install user-service kea-charts/user-service
```

### Upgrade a chart

```bash
helm upgrade user-service kea-charts/user-service
```

## Development

### Lint charts

```bash
helm lint user-service/
```

### Package charts

```bash
helm package user-service/
```

### Test charts

```bash
helm template user-service user-service/ --debug
```

## Values

Each chart has its own `values.yaml` file with default values. You can override these values by:

1. Creating a custom values file
2. Using `--set` flags
3. Using `--values` flag

Example:

```bash
helm install user-service kea-charts/user-service --values custom-values.yaml
```

## Chart Structure

```
user-service/
├── Chart.yaml          # Chart metadata
├── values.yaml         # Default values
├── templates/          # Kubernetes templates
│   ├── deployment.yaml
│   ├── service.yaml
│   ├── configmap.yaml
│   ├── secret.yaml
│   └── ...
└── tests/              # Test templates
    └── test-connection.yaml
```
