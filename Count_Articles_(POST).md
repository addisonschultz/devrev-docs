# Count Articles (POST)

```http
POST https://api.devrev.ai/articles.count
Content-Type: application/json
```

Get count of articles matching given filter.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.articles.countPost();

```