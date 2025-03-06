# Create Survey

```http
POST https://api.devrev.ai/surveys.create
Content-Type: application/json
```

Creates a schema for survey, which includes name and description of
schema.




## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "name": "x"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.create({
    name: "name"
});

```