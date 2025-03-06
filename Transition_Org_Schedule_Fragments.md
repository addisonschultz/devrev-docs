# Transition Org Schedule Fragments

```http
POST https://api.devrev.ai/org-schedule-fragments.transition
Content-Type: application/json
```

Changes stage of an organization schedule fragment.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedule-fragments.transition \
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
await client.schedules.orgScheduleFragmentsTransition({
    id: "id",
    status: DevRev.OrgScheduleFragmentStatus.Archived
});

```