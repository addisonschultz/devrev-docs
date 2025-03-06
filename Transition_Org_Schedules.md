# Transition Org Schedules

```http
POST https://api.devrev.ai/org-schedules.transition
Content-Type: application/json
```

Publishes or archives an organization schedule.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.transition \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "status": "archived"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesTransition({
    id: "id",
    status: DevRev.OrgScheduleStatus.Archived
});

```