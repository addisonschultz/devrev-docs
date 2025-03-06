# Set Schemas Custom

```http
POST https://api.devrev.ai/schemas.custom.set
Content-Type: application/json
```

Creates or updates a custom schema fragment.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.custom.set \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "app_fragment",
  "app": "app"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customSchemaFragmentsSet({
    type: "tenant_fragment"
});

```