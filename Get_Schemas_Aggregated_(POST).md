# Get Schemas Aggregated (POST)

```http
POST https://api.devrev.ai/schemas.aggregated.get
Content-Type: application/json
```

Gets the aggregated schema.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.aggregated.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_fragment_ids": [
    "custom_schema_fragment_ids",
    "custom_schema_fragment_ids"
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.aggregatedSchemaGetPost({
    customSchemaFragmentIds: ["custom_schema_fragment_ids"]
});

```