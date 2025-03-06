# List Content Template (POST)

```http
POST https://api.devrev.ai/content-template.list
Content-Type: application/json
```

Lists the content templates.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/content-template.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.notifications.contentTemplateListPost();

```