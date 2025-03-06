# Update Org Schedule

```http
POST https://api.devrev.ai/org-schedules.update
Content-Type: application/json
```

Updates an organization schedule.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "default_weekly_org_schedule": {
    "intervals": [
      {
        "from": 1000000,
        "to": 1000000
      },
      {
        "from": 1000000,
        "to": 1000000
      }
    ],
    "period_name": "period_name"
  },
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesUpdate({
    id: "id"
});

```