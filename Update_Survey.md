# Update Survey

```http
POST https://api.devrev.ai/surveys.update
Content-Type: application/json
```

Updates a survey's metadata.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.update({
    id: "id"
});

```