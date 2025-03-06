# Get Content Template (POST)

```http
POST https://api.devrev.ai/content-template.get
Content-Type: application/json
```

Get the content template.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/content-template.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.notifications.contentTemplateGetPost({
    id: "id"
});

```