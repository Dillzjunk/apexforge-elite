# ApexForge Elite Quantum AI Generator

Multi-service Vercel deployment of the ApexForge platform (FastAPI backend + React frontend).

**Source**: Adapted from `laughnand-new/EU-AI-ACT-COMPLIANCE-` for Vercel Services.

## Architecture

| Service   | Root       | Framework         | Public paths     |
|-----------|------------|-------------------|------------------|
| backend   | `backend/` | FastAPI           | `/api/*`, `/ws/*`|
| frontend  | `frontend/`| Create React App  | everything else  |

## Required Environment Variables (set in Vercel project settings)

```
MONGO_URL=mongodb+srv://...
DB_NAME=apexforge
EMERGENT_LLM_KEY=your-key-here
JWT_SECRET_KEY=long-random-string
CORS_ORIGINS=*
REDIS_URL=redis://...          # optional but recommended
```

## Frontend API change

All frontend pages use relative paths:

```js
const API = "/api";
```

so requests stay same-origin and are rewritten to the backend service.

## Deploy

1. Import this repo on [vercel.com/new](https://vercel.com/new)
2. Add the environment variables above
3. Deploy

You will get a single domain that serves both the React SPA and the FastAPI backend under `/api`.

## Original project notes

- Founder account is auto-provisioned on first backend startup (see original README).
- Change the default password immediately.
- Rotate any keys that appeared in the original README.
