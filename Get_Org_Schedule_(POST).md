# Get Org Schedule (POST)

```http
POST https://api.devrev.ai/org-schedules.get
Content-Type: application/json
```

Gets an organization schedule.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/org-schedules.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.schedules.orgSchedulesGetPost({
    id: "id"
});

```