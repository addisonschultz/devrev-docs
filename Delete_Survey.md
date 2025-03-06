# Delete Survey

```http
POST https://api.devrev.ai/surveys.delete
Content-Type: application/json
```

Deletes the specified survey.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.delete({
    id: "id"
});

```