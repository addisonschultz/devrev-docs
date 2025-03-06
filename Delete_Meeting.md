# Delete Meeting

```http
POST https://api.devrev.ai/meetings.delete
Content-Type: application/json
```

Deletes the meeting record.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/meetings.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.meetings.delete({
    id: "id"
});

```