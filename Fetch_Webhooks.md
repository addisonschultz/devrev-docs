# Fetch Webhooks

```http
POST https://api.devrev.ai/webhooks.fetch
Content-Type: application/json
```

Fetches an object via webhook.



## Response Body

- 200: The response to fetching an object for a webhook.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.fetch \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "object": "object"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.webhooks.fetch({
    id: "don:integration:<partition>:devo/<dev-org-id>:webhook/<webhook-id>",
    object: "ISS-12345"
});

```