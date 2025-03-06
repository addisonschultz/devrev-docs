# Count Custom Objects (POST)

```http
POST https://api.devrev.ai/custom-objects.count
Content-Type: application/json
```

Counts custom objects.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/custom-objects.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "leaf_type": "leaf_type"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customObjectsCountPost({
    leafType: "leaf_type"
});

```