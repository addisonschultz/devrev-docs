# List Org Schedules (POST)

```http
POST https://api.devrev.ai/org-schedules.list
Content-Type: application/json
```

Gets list of organization schedules.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "valid_until": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesListPost();

```