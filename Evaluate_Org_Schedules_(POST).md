# Evaluate Org Schedules (POST)

```http
POST https://api.devrev.ai/org-schedules.evaluate
Content-Type: application/json
```

Evaluates an organization's schedule at specified instants.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.evaluate \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "instants": [
    "instants",
    "instants"
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesEvaluatePost({
    id: "id",
    instants: [new Date("2023-01-01T12:00:00.000Z")]
});

```