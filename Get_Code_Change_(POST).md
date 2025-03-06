# Get Code Change (POST)

```http
POST https://api.devrev.ai/code-changes.get
Content-Type: application/json
```

Gets a code change object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/code-changes.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.codeChanges.getPost({
    id: "id"
});

```