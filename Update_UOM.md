# Update UOM

```http
POST https://api.devrev.ai/uoms.update
Content-Type: application/json
```

Updates a Unit of Measurement.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "aggregation_type": "duration",
  "dimensions": {},
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsUpdate({
    id: "id"
});

```