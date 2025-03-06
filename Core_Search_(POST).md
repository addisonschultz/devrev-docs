# Core Search (POST)

```http
POST https://api.devrev.ai/search.core
Content-Type: application/json
```

Searches for records based on a given query.



## Response Body

- 200: Search response.

## Examples

```shell
curl -X POST https://api.devrev.ai/search.core \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "query": "query",
  "sort_by": "created_date",
  "sort_order": "asc"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.search.corePost({
    query: "query"
});

```