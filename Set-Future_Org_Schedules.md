# Set-Future Org Schedules

```http
POST https://api.devrev.ai/org-schedules.set-future
Content-Type: application/json
```

Sets next organization schedule fragment which must begin the day the
last existing fragment ends.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.set-future \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "org_schedule_fragment_id": "org_schedule_fragment_id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesSetFuture({
    id: "id",
    orgScheduleFragmentId: "org_schedule_fragment_id"
});

```