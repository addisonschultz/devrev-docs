# Create Org Schedule

```http
POST https://api.devrev.ai/org-schedules.create
Content-Type: application/json
```

Creates an organization schedule with a default weekly organization
schedule and a list of organization schedule fragments.




## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.create \
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
  "name": "name",
  "timezone": "timezone"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesCreate({
    name: "name",
    timezone: "timezone"
});

```