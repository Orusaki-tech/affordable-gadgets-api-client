# API Client Generation

This shared repo hosts the OpenAPI spec and the generated TypeScript API client for all frontends.

## Regenerating API Clients

When the backend API changes:

1. **Export or copy the latest OpenAPI spec from the backend into this repo**
2. **Run the generation script from this repo:**
   ```bash
   ./scripts/generate-api.sh
   ```

This rebuilds the shared client package used by all frontends.

## Manual Generation

If you prefer to generate manually:

```bash
cd packages/api-client
npx openapi-typescript-codegen \
  --input ../../openapi.yaml \
  --output src \
  --client axios
```

## Notes

- The generated client lives in `packages/api-client`
- Always commit the generated files to version control
- `openapi.yaml` should be updated from the backend, not edited here
