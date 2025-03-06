# Update Engagement

```http
POST https://api.devrev.ai/engagements.update
Content-Type: application/json
```

Updates the engagement record.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/engagements.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "artifacts": {},
  "id": "id",
  "members": {},
  "parents": {},
  "tags": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.engagements.update({
    id: "id"
});

```