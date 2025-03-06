# Export Conversations (POST)

```http
POST https://api.devrev.ai/conversations.export
Content-Type: application/json
```

Exports a collection of conversation items.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.export \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "modified_date": {},
  "sla_summary": {
    "target_time": {
      "type": "preset",
      "preset_type": "last_n_days",
      "days": 4294967295
    }
  },
  "stage": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.conversations.exportPost();

```