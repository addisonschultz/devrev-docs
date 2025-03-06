# Get Engagement (POST)

```http
POST https://api.devrev.ai/engagements.get
Content-Type: application/json
```

Gets the engagement record.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/engagements.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.engagements.getPost({
    id: "id"
});

```