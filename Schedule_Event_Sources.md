# Schedule Event Sources

```http
POST https://api.devrev.ai/event-sources.schedule
Content-Type: application/json
```

Schedules an event to be published to the specified event source.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/event-sources.schedule \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "event_type": "event_type",
  "id": "id",
  "payload": "payload"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.eventSource.eventSourcesScheduleEvent({
    eventType: "event_type",
    id: "id",
    payload: "payload"
});

```