# Get Incident (POST)

```http
POST https://api.devrev.ai/incidents.get
Content-Type: application/json
```

Gets an incident.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.operate.incidentsGetPost({
    id: "id"
});

```