# Hermes Architecture

## System Overview

```
┌─────────────────────────────────────────┐
│         Client Applications             │
└────────────────┬────────────────────────┘
                 │
         ┌───────▼────────┐
         │  API Gateway   │ (Port 8080)
         │  - Routing     │
         │  - Health Chks │
         │  - Aggregation │
         └───┬────┬────┬──┘
             │    │    │
    ┌────────┘    │    └──────────┐
    │             │               │
    ▼             ▼               ▼
 ┌────────┐  ┌─────────┐  ┌──────────────┐
 │ASSIST_ │  │ Ruflo   │  │ GStack       │
 │OS      │  │         │  │              │
 │:3000   │  │:3001    │  │:3002         │
 │        │  │         │  │              │
 │Policy  │  │Collab   │  │Agents        │
 │Engine  │  │Engine   │  │Orchestration │
 └────────┘  └─────────┘  └──────────────┘
    │            │              │
    └────────────┼──────────────┘
                 │
    ┌────────────▼──────────────┐
    │  Shared Infrastructure    │
    │  - Configuration          │
    │  - Logging                │
    │  - Event Bus (optional)   │
    │  - Database (optional)    │
    └───────────────────────────┘
```

## Service Details

### ASSIST_OS (Port 3000)
**Governance & Policy Framework**

Responsibilities:
- Policy enforcement
- Role-based access control
- Audit logging
- Compliance management

Technology:
- Node.js runtime
- Express.js framework
- Policy engine

### Ruflo (Port 3001)
**Real-time Collaboration Platform**

Responsibilities:
- Real-time synchronization
- Knowledge management
- Presence tracking
- Conflict resolution

Technology:
- WebSocket support
- Event-driven architecture
- State management

### GStack (Port 3002)
**Enterprise Agent Framework**

Responsibilities:
- Agent orchestration
- Workflow management
- Pattern library
- Integration factory

Technology:
- 70+ agent modules
- Workflow engine
- SDK framework

### API Gateway (Port 8080)
**Unified Router**

Responsibilities:
- Request routing
- Load balancing
- Health monitoring
- Service aggregation

Technology:
- Node.js HTTP server
- Express.js
- JSON APIs

## Data Flow

1. **Client Request** → API Gateway (8080)
2. **Routing** → Appropriate Service
3. **Processing** → Service Logic
4. **Optional**: Cross-service communication
5. **Response** → Aggregated via Gateway
6. **Return** → Client

## Communication Patterns

### Service-to-Service
- HTTP/REST APIs
- Optional: Redis Pub/Sub for events
- Optional: Shared database

### Client-to-Service
- REST APIs via Gateway
- WebSocket for real-time (Ruflo)
- Health check endpoints

## Configuration

Central configuration: `config/hermes.config.json`

Service-specific config in each service directory.

## Deployment Topology

```
Local Development
  └─ 4 processes (assist-os, ruflo, gstack, gateway)

Staging
  └─ Docker Compose with shared database

Production
  └─ Kubernetes with:
     - Load Balancer
     - Multiple replicas
     - Persistent storage
     - Monitoring
```

## Scaling Strategy

### Horizontal
1. Add load balancer
2. Deploy multiple instances
3. Use shared database
4. Implement caching layer

### Vertical
1. Increase memory allocation
2. Configure threading
3. Enable compression
4. Optimize queries

## Security Layers

1. **Network**: Firewall rules
2. **Authentication**: JWT/OAuth2
3. **Authorization**: RBAC via ASSIST_OS
4. **Transport**: TLS/SSL
5. **Secrets**: Vault/K8s secrets
6. **Audit**: Logging via ASSIST_OS

## Monitoring Points

- Service health endpoints
- Response times
- Error rates
- Resource usage
- Database connectivity
- Cache hit rates
