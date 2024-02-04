# Sveltekit/Pocketbase/Dokku Monorepo Quick Starter

## Getting started (Local)

The following files need to be modified with the correct values:

### Replace "project_name" in files

- .dokku-monorepo
- package.json

### Replace `.env` variables

```bash
PUBLIC_POCKETBASE_URL=http://127.0.0.1:8090
```

### Setup pocketbase

- Run the following commands:

```bash
cd ./sveltekit
npm install
npm run pb:serve
```

- Navigate to the Pocketbase url and perform initial setup, desired schemas, and configurations.
- Generate types `npm run pb:types`

## Deploying to Dokku

`TODO: instructions coming soon`
