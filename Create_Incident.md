# Create Incident

```http
POST https://api.devrev.ai/incidents.create
Content-Type: application/json
```

Creates an incident.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "impact": {},
  "stage": {
    "stage": "stage"
  },
  "title": "title"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.operate.incidentsCreate({
    title: "title"
});

```