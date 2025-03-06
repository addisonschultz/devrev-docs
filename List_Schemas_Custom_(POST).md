# List Schemas Custom (POST)

```http
POST https://api.devrev.ai/schemas.custom.list
Content-Type: application/json
```

Lists custom schema fragments.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.custom.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customSchemaFragmentsListPost();

```