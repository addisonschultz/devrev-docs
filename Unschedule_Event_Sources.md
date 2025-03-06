# Unschedule Event Sources

```http
POST https://api.devrev.ai/event-sources.unschedule
Content-Type: application/json
```

Deletes an event scheduled for the specified event source.



## Examples

```shell
curl -X POST https://api.devrev.ai/event-sources.unschedule \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "event_key": "event_key",
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.eventSource.eventSourcesDeleteScheduledEvent({
    eventKey: "event_key",
    id: "id"
});

```