# Create Engagement

```http
POST https://api.devrev.ai/engagements.create
Content-Type: application/json
```

Creates a new engagement record.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/engagements.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "engagement_type": "call",
  "members": [
    "members",
    "members"
  ],
  "scheduled_date": "scheduled_date",
  "title": "title"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.engagements.create({
    members: ["DEVU-12345"],
    scheduledDate: new Date("2023-01-01T12:00:00.000Z"),
    title: "title"
});

```