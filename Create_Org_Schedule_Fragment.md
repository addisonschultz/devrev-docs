# Create Org Schedule Fragment

```http
POST https://api.devrev.ai/org-schedule-fragments.create
Content-Type: application/json
```

Creates an organization schedule fragment.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedule-fragments.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "from": "from",
  "intervals": [
    {
      "from": "from",
      "name": "name"
    },
    {
      "from": "from",
      "name": "name"
    }
  ],
  "name": "name",
  "to": "to"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgScheduleFragmentsCreate({
    from: new Date("2023-01-01T12:00:00.000Z"),
    intervals: [{
            from: new Date("2023-01-01T12:00:00.000Z"),
            name: "name"
        }],
    name: "name",
    to: new Date("2023-01-01T12:00:00.000Z")
});

```