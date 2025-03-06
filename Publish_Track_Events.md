# Publish Track Events

```http
POST https://api.devrev.ai/track-events.publish
Content-Type: application/json
```

Allows publishing of events (example from plug widget).



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/track-events.publish \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "events_list": [
    {
      "client_context": {
        "browser": {},
        "cpu": {},
        "device": {},
        "engine": {},
        "os": {},
        "page": {}
      },
      "name": "name",
      "payload": {}
    },
    {
      "client_context": {
        "browser": {},
        "cpu": {},
        "device": {},
        "engine": {},
        "os": {},
        "page": {}
      },
      "name": "name",
      "payload": {}
    }
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.eventSource.trackEventsPublish({
    eventsList: [{
            name: "name",
            payload: {
                "key": "value"
            }
        }]
});

```