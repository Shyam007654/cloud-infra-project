# Local Cloud Infrastructure & Observability Simulation

A zero-cost local CloudOps environment built with **Docker Compose**, **Nginx**, **cAdvisor**, **Prometheus**, and **Grafana** to simulate load balancing, container health monitoring, and high availability.

## Architecture

- **Load Balancer (`:8080`)**: Nginx reverse proxy distributing traffic across multiple backend containers (`web1`, `web2`, `web3`) with automatic container restart policies.
- **Metrics Collector (`:8081`)**: cAdvisor collecting real-time container CPU, memory, and resource metrics.
- **Time-Series Database (`:9090`)**: Prometheus scraping container metrics every 5 seconds.
- **Monitoring Dashboard (`:3000`)**: Grafana visualizing live container performance metrics.

## How to Run

Start the full stack:

```bash
docker compose up -d
```

Verify running containers:

```bash
docker ps
```

Open in browser:

- Load Balancer: `http://localhost:8080`
- Grafana Dashboard: `http://localhost:3000`

Stop and clean up containers:

```bash
docker compose down
```

## Key Features Demonstrated

- Round-robin traffic distribution across backend instances
- Auto-restart / failover resilience at the container level
- Real-time container observability without cloud billing overhead
