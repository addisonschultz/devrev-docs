# Get-Reply Recommendations

```http
POST https://api.devrev.ai/recommendations.get-reply
Content-Type: application/json
```

Gets a reply for a user query.



## Response Body

- 200: The response for the generated reply.

## Examples

```shell
curl -X POST https://api.devrev.ai/recommendations.get-reply \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "query": "x"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.recommendations.getReply({
    query: "query"
});

```