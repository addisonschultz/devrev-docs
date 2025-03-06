# Update Meeting

```http
POST https://api.devrev.ai/meetings.update
Content-Type: application/json
```

Updates the meeting record.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/meetings.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "channel": "amazon_connect",
  "custom_schema_spec": {},
  "id": "id",
  "members": {},
  "state": "canceled",
  "tags": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.meetings.update({
    id: "id"
});

```