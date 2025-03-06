# Count Meetings (POST)

```http
POST https://api.devrev.ai/meetings.count
Content-Type: application/json
```

Counts the meeting records.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/meetings.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "ended_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "modified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "scheduled_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.meetings.countPost();

```