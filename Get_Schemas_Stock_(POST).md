# Get Schemas Stock (POST)

```http
POST https://api.devrev.ai/schemas.stock.get
Content-Type: application/json
```

Gets a stock schema fragment.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.stock.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.stockSchemaFragmentsGetPost();

```