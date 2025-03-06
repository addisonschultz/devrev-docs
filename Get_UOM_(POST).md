# Get UOM (POST)

```http
POST https://api.devrev.ai/uoms.get
Content-Type: application/json
```

Gets a Unit of Measurement.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsGetPost({
    id: "id"
});

```