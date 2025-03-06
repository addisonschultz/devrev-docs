# Update Snap In

```http
POST https://api.devrev.ai/snap-ins.update
Content-Type: application/json
```

Updates a snap-in.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/snap-ins.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.snapIns.update({
    id: "id"
});

```