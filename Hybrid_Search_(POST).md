# Hybrid Search (POST)

```http
POST https://api.devrev.ai/search.hybrid
Content-Type: application/json
```

Performs search, using a combination of syntactic and semantic search.




## Response Body

- 200: Hybrid search response.

## Examples

```shell
curl -X POST https://api.devrev.ai/search.hybrid \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "namespace": "account",
  "query": "x"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.search.hybridPost({
    namespace: DevRev.SearchHybridNamespace.Article,
    query: "query"
});

```