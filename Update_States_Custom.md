# Update States Custom

```http
POST https://api.devrev.ai/states.custom.update
Content-Type: application/json
```

Updates a custom state.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/states.custom.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStatesUpdate({
    id: "id"
});

```