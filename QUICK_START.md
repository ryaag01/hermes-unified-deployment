# Quick Start Guide

## 1. Prerequisites
- Node.js v16 or higher
- npm or yarn
- 4 GB RAM minimum

## 2. Local Setup

### Extract Files
```bash
cd hermes-unified-1781630409
```

### Install Dependencies

**Terminal 1:**
```bash
cd services/assist-os
npm install
```

**Terminal 2:**
```bash
cd services/ruflo
npm install
```

**Terminal 3:**
```bash
cd services/gstack
npm install
```

## 3. Start Services

**Terminal 1 - ASSIST_OS (Port 3000):**
```bash
cd services/assist-os
npm start
```

**Terminal 2 - Ruflo (Port 3001):**
```bash
cd services/ruflo
npm start
```

**Terminal 3 - GStack (Port 3002):**
```bash
cd services/gstack
npm start
```

**Terminal 4 - API Gateway (Port 8080):**
```bash
node config/gateway.js
```

## 4. Verify Services

### Check Gateway Health
```bash
curl http://localhost:8080/health
```

### Check Individual Services
```bash
curl http://localhost:3000/health  # ASSIST_OS
curl http://localhost:3001/health  # Ruflo
curl http://localhost:3002/health  # GStack
```

## 5. Access Services

- **API Gateway**: http://localhost:8080
- **ASSIST_OS**: http://localhost:3000
- **Ruflo**: http://localhost:3001
- **GStack**: http://localhost:3002

## Troubleshooting

### Port Already in Use
```bash
lsof -i :PORT
```

### Missing Dependencies
```bash
cd services/SERVICE_NAME
npm install --legacy-peer-deps
```

### Service Not Starting
Check logs in `logs/` directory or check service-specific output.

## Next Steps

1. Review DEPLOYMENT_MANIFEST.md for detailed configuration
2. Check service documentation in each services/ subdirectory
3. Configure database and cache for production
4. Setup monitoring and alerting
