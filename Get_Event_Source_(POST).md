# Get Event Source (POST)

```http
POST https://api.devrev.ai/event-sources.get
Content-Type: application/json
```

Gets an event source.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/event-sources.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.eventSource.eventSourcesGetPost({
    id: "id"
});

```