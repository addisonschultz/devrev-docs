# Count UOMs (POST)

```http
POST https://api.devrev.ai/uoms.count
Content-Type: application/json
```

Counts the number of Unit of Measurements based on the given filters.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsCountPost();

```