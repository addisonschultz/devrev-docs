# List Custom Objects (POST)

```http
POST https://api.devrev.ai/custom-objects.list
Content-Type: application/json
```

Lists custom objects.



## Response Body

- 200: The response to listing all custom objects matching the filter
criteria.


## Examples

```shell
curl -X POST https://api.devrev.ai/custom-objects.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "leaf_type": "leaf_type",
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customObjectsListPost({
    leafType: "leaf_type"
});

```