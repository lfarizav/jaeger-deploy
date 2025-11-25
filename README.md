# Jaeger Deploy

Jaeger distributed tracing deployment for Keptn observability.

## Overview

This repository manages the deployment of Jaeger for distributed tracing, integrated with Keptn for observability.

## Architecture

- **Namespace**: `jaeger`
- **Deployment**: Jaeger All-in-One (suitable for development/testing)
- **Integration**: Keptn Lifecycle Toolkit sends traces to Jaeger

## Components

- **Jaeger All-in-One**: Combines collector, query, and UI in a single deployment
- **Service**: Exposed on port 16686 (UI) and 14250 (gRPC collector)

## Deployment

This repository is automatically deployed by Flux CD when:

1. Changes are pushed to the `main` branch
2. Flux reconciles (every 5 minutes)

## Access

Jaeger UI is accessible at:
- NodePort: `http://<node-ip>:30686`

## Integration with Keptn

Keptn is configured to send traces to Jaeger collector at:
- `jaeger-collector.jaeger.svc.cluster.local:14250` (gRPC)
