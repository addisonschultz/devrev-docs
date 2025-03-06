# Count Engagements (POST)

```http
POST https://api.devrev.ai/engagements.count
Content-Type: application/json
```

Counts the engagement records.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/engagements.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.engagements.countPost();

```