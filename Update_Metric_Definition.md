# Update Metric Definition

```http
POST https://api.devrev.ai/metric-definitions.update
Content-Type: application/json
```

Updates a custom metric definition



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-definitions.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "status": "active"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.slas.metricDefinitionsUpdate({
    id: "id"
});

```