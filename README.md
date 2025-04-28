Description

A multi‑tenant back‑end platform (OPaaS) offering account management, a facial‑mesh asset repository, order orchestration, invoicing and subscription billing. Built for 99.9% API SLA, <200 ms average query, PCI‑DSS & PIPEDA compliance.

Tech Stack

Language & Runtimes: Python 3.12 (FastAPI microservices), TypeScript (Apollo GraphQL)

Databases: PostgreSQL 16 + PostGIS (Aurora Serverless v3), Snowflake for analytics

Infrastructure: Docker, AWS Aurora Serverless v3, Snowflake

Compliance: PCI‑DSS & PIPEDA ready

Key Features

Multi‑tenant account store

Facial‑mesh upload & retrieval (PostGIS + S3)

Order orchestration & status workflows

Invoice generation & subscription engine

backend/
├── README.md
├── docker-compose.yml
├── services/
│   ├── accounts/          # Python FastAPI service
│   │   ├── app.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── crud.py
│   │   └── Dockerfile
│   ├── meshrepo/          # Python FastAPI service
│   │   ├── app.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── crud.py
│   │   └── Dockerfile
│   ├── orders/            # Python FastAPI service
│   │   ├── app.py
│   │   ├── models.py
│   │   ├── schemas.py
│   │   ├── crud.py
│   │   └── Dockerfile
│   └── billing/           # Python FastAPI service
│       ├── app.py
│       ├── models.py
│       ├── schemas.py
│       ├── crud.py
│       └── Dockerfile
├── graphql/               # TypeScript GraphQL gateway
│   ├── schema.graphql
│   ├── src/
│   │   ├── index.ts
│   │   ├── resolvers.ts
│   │   └── Dockerfile
│   └── package.json
└── infra/
    ├── sql/
    │   ├── tenants.sql
    │   ├── mesh.sql
    │   ├── orders.sql
    │   └── billing.sql
    └── snowflake/
        ├── warehouse.sql
        └── roles.sql

        # Core SaaS / OPaaS Back‑End

## Overview
This repository contains microservices and a GraphQL gateway for a multi‑tenant OPaaS platform. Services are Docker‑containerized and use AWS Aurora Serverless v3 (PostgreSQL 16 + PostGIS) and Snowflake.

### Components
- `accounts`: user & tenant management
- `meshrepo`: facial‑mesh asset storage (PostGIS + S3)
- `orders`: order orchestration workflows
- `billing`: invoice & subscription engine
- `graphql`: Apollo GraphQL gateway

## Prerequisites
- Docker & Docker Compose
- AWS credentials (Aurora Serverless endpoint)
- Snowflake account & credentials

## Setup
1. **Clone**
   ```bash
   git clone https://github.com/yourorg/core-saas-opaas-backend.git
   cd core-saas-opaas-backend/backend
