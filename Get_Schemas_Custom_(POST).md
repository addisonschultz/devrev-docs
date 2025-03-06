# Get Schemas Custom (POST)

```http
POST https://api.devrev.ai/schemas.custom.get
Content-Type: application/json
```

Gets a custom schema fragment.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.custom.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customSchemaFragmentsGetPost({
    id: "id"
});

```