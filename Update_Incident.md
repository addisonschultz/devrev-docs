# Update Incident

```http
POST https://api.devrev.ai/incidents.update
Content-Type: application/json
```

Updates an incident.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "applies_to_parts": {},
  "artifacts": {},
  "custom_schema_spec": {},
  "id": "id",
  "impact": {
    "customer_ids": {}
  },
  "owned_by": {},
  "pia": {},
  "playbooks": {},
  "related_docs": {},
  "stage": {},
  "tags": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.operate.incidentsUpdate({
    id: "id"
});

```