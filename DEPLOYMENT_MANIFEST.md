# Deployment Manifest

## Overview

Complete deployment guide for Hermes unified platform.

## Components

### ASSIST_OS (Port 3000)
- Governance kernel
- Policy enforcement
- RBAC implementation
- Audit logging

### Ruflo (Port 3001)
- Collaboration platform
- Knowledge management
- Real-time sync
- Presence tracking

### GStack (Port 3002)
- Agent framework
- Workflow orchestration
- 70+ modules
- Integration patterns

### API Gateway (Port 8080)
- Unified routing
- Load balancing
- Health checks
- Service aggregation

## Deployment Steps

1. Extract deployment files
2. Install dependencies per service
3. Configure environment
4. Start services
5. Verify health
6. Monitor logs

## Port Mapping

- 8080: API Gateway
- 3000: ASSIST_OS
- 3001: Ruflo
- 3002: GStack
- 5432: PostgreSQL (optional)
- 6379: Redis (optional)

## Health Checks

All services expose `/health` endpoint.

```bash
curl http://localhost:8080/health
```

## Configuration

See `config/hermes.config.json`

## Troubleshooting

Check logs in `logs/` directory.

## Support

See README.md and service-specific documentation.
