# List Schemas Stock (POST)

```http
POST https://api.devrev.ai/schemas.stock.list
Content-Type: application/json
```

Lists stock schema fragments.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.stock.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "filter_preset": "customizable_types_preset",
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.stockSchemaFragmentsListPost();

```