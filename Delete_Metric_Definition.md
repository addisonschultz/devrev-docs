# Delete Metric Definition

```http
POST https://api.devrev.ai/metric-definitions.delete
Content-Type: application/json
```

Deletes a custom metric definition



## Response Body

- 204: The response to deleting a metric definition.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-definitions.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.slas.metricDefinitionsDelete({
    id: "id"
});

```