# Create Custom Object

```http
POST https://api.devrev.ai/custom-objects.create
Content-Type: application/json
```

Creates a custom object.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/custom-objects.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "leaf_type": "leaf_type",
  "unique_key": "unique_key"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customObjectsCreate({
    leafType: "leaf_type",
    uniqueKey: "unique_key"
});

```