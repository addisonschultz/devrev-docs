# Delete Incident

```http
POST https://api.devrev.ai/incidents.delete
Content-Type: application/json
```

Deletes an incident.



## Response Body

- 200: The response to deleting the incident.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.operate.incidentsDelete({
    id: "id"
});

```