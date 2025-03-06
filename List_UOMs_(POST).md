# List UOMs (POST)

```http
POST https://api.devrev.ai/uoms.list
Content-Type: application/json
```

Gets the Unit of Measurements based on the given filters.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsListPost();

```