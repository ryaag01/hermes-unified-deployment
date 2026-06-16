# 🚀 Hermes Unified Deployment v1.0.0

**Complete integration of ASSIST_OS + Ruflo + GStack**

Full-stack enterprise deployment with governance, collaboration, and agent orchestration.

## 📋 Overview

Hermes is a unified deployment platform combining three major systems:

- **ASSIST_OS** - Governance & Policy Framework
- **Ruflo** - Real-time Collaboration Platform
- **GStack** - Enterprise Agent Framework
- **API Gateway** - Unified Router & Load Balancer

## 🎯 Key Features

✅ Unified Architecture - 4 services integrated seamlessly
✅ Microservices - Independent service scaling
✅ API Gateway - Single entry point with routing
✅ Production-Ready - Enterprise deployment structure
✅ Zero-Docker Option - Run locally without containers
✅ Comprehensive Docs - Complete implementation guides
✅ Health Checks - Built-in service monitoring
✅ Modular Design - Easy to extend and customize

## 🚀 Quick Start

### Prerequisites
- Node.js v16+
- npm or bun

### Local Deployment (4 terminals)

**Terminal 1 - ASSIST_OS**
```bash
cd services/assist-os
npm install && npm start
```

**Terminal 2 - Ruflo**
```bash
cd services/ruflo
npm install && npm start
```

**Terminal 3 - GStack**
```bash
cd services/gstack
npm install && npm start
```

**Terminal 4 - API Gateway**
```bash
node config/gateway.js
```

### Verify Deployment
```bash
curl http://localhost:8080/health
```

## 📍 Service Endpoints

| Service | Port | Purpose |
|---------|------|----------|
| API Gateway | 8080 | Unified entry point |
| ASSIST_OS | 3000 | Governance & policy |
| Ruflo | 3001 | Collaboration |
| GStack | 3002 | Agent orchestration |

## 🏗️ Architecture

```
┌─────────────────────────────────────┐
│    API Gateway (Port 8080)          │
│    • Routing • Load Balancing       │
├─────────────────────────────────────┤
│  ┌──────────┬────────┬───────────┐  │
│  │ASSIST_OS │ Ruflo  │ GStack    │  │
│  │ :3000    │ :3001  │ :3002     │  │
│  └──────────┴────────┴───────────┘  │
├─────────────────────────────────────┤
│  Shared Config, Logging, Monitoring │
└─────────────────────────────────────┘
```

## 📚 Documentation

- DEPLOYMENT_MANIFEST.md - Detailed deployment guide
- config/hermes.config.json - Service configuration
- deploy-hermes.sh - Docker deployment automation

## 🔧 Components

### ASSIST_OS (Port 3000)
- Policy enforcement engine
- Role-based access control (RBAC)
- Audit logging
- Compliance management

### Ruflo (Port 3001)
- Knowledge management system
- Presence and awareness
- Real-time synchronization
- Conflict resolution

### GStack (Port 3002)
- 70+ specialized agent modules
- Workflow orchestration
- Design pattern library
- Integration factory

### API Gateway (Port 8080)
- Request routing to services
- Load balancing
- Health checks
- Service aggregation

## 📋 Configuration

Central configuration at `config/hermes.config.json`

## 🔍 Monitoring

### Health Check
```bash
curl http://localhost:8080/health
```

## 🚨 Troubleshooting

### Port Already in Use
```bash
lsof -i :PORT
```

### Dependencies Missing
```bash
cd services/SERVICE_NAME
npm install --legacy-peer-deps
npm start
```

## 🐳 Docker Deployment

```bash
bash deploy-hermes.sh production
```

## 📊 Project Structure

```
hermes-unified/
├── services/
│   ├── assist-os/        # Governance
│   ├── ruflo/            # Collaboration
│   └── gstack/           # Agents
├── config/
│   ├── hermes.config.json
│   └── gateway.js
├── logs/
├── docs/
└── deploy-hermes.sh
```

## ✨ Version

**v1.0.0** - Initial unified deployment (2026-06-16)

## 📜 License

MIT License

---

**Status**: Ready for Deployment ✅
**Last Updated**: 2026-06-16