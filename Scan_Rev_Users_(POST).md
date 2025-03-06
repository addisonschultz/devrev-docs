# Scan Rev Users (POST)

```http
POST https://api.devrev.ai/rev-users.scan
Content-Type: application/json
```

Scans through all Rev users.



## Response Body

- 200: The response to scanning Rev users.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.scan \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {},
  "modified_date": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.revUsers.scanPost();

```