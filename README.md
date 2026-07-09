# IAS Research Backend

NestJS backend with Prisma (PostgreSQL), Redis, and ChromaDB.

## Prerequisites

- Node.js
- Docker & Docker Compose

## Infrastructure (Docker Compose)

Start services:

```bash
docker compose up -d
```

Services:
- PostgreSQL: `5432`
- Redis: `6379`
- ChromaDB: `8000`

## Environment Variables

Template env file ada di:
- `.env.example`

Copy template ke local env:

```bash
copy .env.example .env
```

Default values (sesuai `.env.example`):
- `DATABASE_URL=postgresql://ias_user:ias_password@localhost:5432/ias_research_db?schema=public`
- `REDIS_HOST=localhost`, `REDIS_PORT=6379`
- `CHROMA_URL=http://localhost:8000`

## Database Setup (Prisma)

Jalankan migration:

```bash
npx prisma migrate dev
```

Jika belum ada migration, Prisma akan membuat migration pertama.

## Run Backend

```bash
pnpm install
pnpm start:dev
```

Backend berjalan di:
- `http://localhost:3000`

## Scripts

- `pnpm start:dev` — start development
- `pnpm build` — build
- `pnpm test` — unit tests
- `pnpm test:e2e` — e2e tests
- `pnpm lint` — eslint

