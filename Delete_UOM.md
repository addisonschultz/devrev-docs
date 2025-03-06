# Delete UOM

```http
POST https://api.devrev.ai/uoms.delete
Content-Type: application/json
```

Deletes a Unit of Measurement.



## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsDelete({
    id: "id"
});

```