# Create Meeting

```http
POST https://api.devrev.ai/meetings.create
Content-Type: application/json
```

Creates a new meeting record.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/meetings.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "channel": "amazon_connect",
  "custom_schema_spec": {},
  "members": [
    "members",
    "members"
  ],
  "scheduled_date": "scheduled_date",
  "state": "canceled",
  "title": "title"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.meetings.create({
    channel: DevRev.MeetingChannel.GoogleMeet,
    endedDate: new Date("2023-01-01T12:00:00.000Z"),
    members: ["DEVU-12345"],
    scheduledDate: new Date("2023-01-01T12:00:00.000Z"),
    state: DevRev.MeetingState.Canceled,
    title: "title"
});

```