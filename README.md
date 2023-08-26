# MiniKube DevOps Project

This project showcases a local Kubernetes environment using Minikube, integrated with tools like Istio, ArgoCD, Prometheus, Grafana, and Alertmanager.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Setup](#setup)
  - [Minikube](#minikube)
  - [Istio](#istio)
  - [ArgoCD](#argocd)
  - [Prometheus](#prometheus)
  - [Grafana](#grafana)
  - [Alertmanager](#alertmanager)
- [Accessing Services](#accessing-services)
- [Contributing](#contributing)

## Prerequisites

- Minikube
- kubectl
- ArgoCD CLI
- Istio CLI

## Setup

### Minikube

Start Minikube:

```bash
minikube start
```

### Istio

Install Istio:

```bash
istioctl install
```

Deploy the Bookinfo sample application:

```bash
kubectl apply -f <path_to_bookinfo_manifest>
```

### ArgoCD

Deploy ArgoCD:

```bash
kubectl apply -n argocd -f <path_to_argocd_manifest>
```

### Prometheus

Deploy Prometheus in the `monitoring` namespace:

```bash
kubectl apply -n monitoring -f <path_to_prometheus_manifest>
```

### Grafana

Deploy Grafana in the `monitoring` namespace:

```bash
kubectl apply -n monitoring -f <path_to_grafana_manifest>
```

### Alertmanager

Deploy Alertmanager in the `monitoring` namespace:

```bash
kubectl apply -n monitoring -f <path_to_alertmanager_manifest>
```

## Accessing Services

- **Prometheus**: `kubectl port-forward -n monitoring svc/prometheus <local_port>:9090`
- **Grafana**: `kubectl port-forward -n monitoring svc/grafana <local_port>:3000`
- **Alertmanager**: `kubectl port-forward -n monitoring svc/alertmanager <local_port>:9093`
- **ArgoCD**: `kubectl port-forward svc/argocd-server -n argocd <local_port>:443`

Replace `<local_port>` with your desired local port.

## Contributing

1. Fork the repository.
2. Create a new feature branch.
3. Make your changes.
4. Submit a pull request.
