# Get Org Schedule Fragment (POST)

```http
POST https://api.devrev.ai/org-schedule-fragments.get
Content-Type: application/json
```

Gets an organization schedule fragment.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedule-fragments.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgScheduleFragmentsGetPost({
    id: "id"
});

```