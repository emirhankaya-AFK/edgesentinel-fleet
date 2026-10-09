# EdgeSentinel: Edge AI Vision Fleet Management

EdgeSentinel is a comprehensive portfolio product for managing fleets of edge AI vision devices. It provides device registration, heartbeat monitoring, camera stream simulation, model registry with immutable versions and rollout states, inference event ingestion, alert acknowledgement, human review/feedback loop, drift metrics computation, offline edge queue with retry/sync behavior, audit logging, and a role-ready architecture.

## Features

- **Device Management**: Register and monitor edge devices via heartbeats
- **Model Registry**: Store and manage AI model versions with immutability flags and rollout states
- **Event Ingestion**: Receive and process inference events from edge devices
- **Alerting**: Generate alerts based on drift, low confidence, or anomalies
- **Human Review**: Workflow for human feedback on inferences
- **Drift Detection**: Compute drift metrics from event confidence and feature statistics
- **Offline Support**: Edge agent queues events during offline periods and syncs when back online
- **Audit Log**: Comprehensive audit trail for all system actions
- **Role-Ready Architecture**: Designed to support role-based access control (RBAC)

## Architecture

See [docs/architecture.md](docs/architecture.md) for detailed architecture diagrams and explanations.

## API Documentation

See [docs/api.md](docs/api.md) for REST API and WebSocket event feed documentation.

## Threat Model

See [docs/threat_model.md](docs/threat_model.md) for security considerations and threat mitigation strategies.

## Getting Started

### Prerequisites

- Docker and Docker Compose
- (Optional) Kubernetes cluster for production deployment

### Running with Docker Compose

1. Clone the repository
2. Navigate to the project directory
3. Copy the example environment file:
   ```bash
   cp backend/.env.example backend/.env
   ```
4. Edit the `.env` file if needed (for PostgreSQL connection)
5. Start the services:
   ```bash
   make up
   ```
6. Access the dashboard at http://localhost:3000
7. The backend API will be available at http://localhost:8000

### Running with Kubernetes

1. Apply the database storage class and PVC (if not already available)
2. Apply the Kubernetes manifests:
   ```bash
   kubectl apply -f kubernetes/
   ```
3. Access the frontend via the LoadBalancer service or set up an Ingress

### Sample Data

To populate the database with sample data, run the sample data script:
```bash
# Using Docker Compose
docker-compose run --rm backend python kubernetes/scripts/sample_data.py

# Using Kubernetes
kubectl run --rm -i --tty sample-data --image=edgesentinel-backend:latest --restart=Never -- \
  python kubernetes/scripts/sample_data.py
```

## Development

### Backend

- Technology: FastAPI, SQLAlchemy, Pydantic
- Testing: Run `make test` to execute backend tests

### Frontend

- Technology: React, TypeScript, Vite
- Development: `make frontend` starts the frontend in development mode

### Edge Agent Simulator

- Technology: Python
- Purpose: Simulates edge devices generating synthetic vision data

## License

This project is proprietary and confidential. All rights reserved.

## Contact

For inquiries, please contact [your contact information here].