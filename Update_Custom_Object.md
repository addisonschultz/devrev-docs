# Update Custom Object

```http
POST https://api.devrev.ai/custom-objects.update
Content-Type: application/json
```

Updates a custom object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/custom-objects.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customObjectsUpdate({
    id: "id"
});

```