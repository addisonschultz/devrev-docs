# Delete Code Change

```http
POST https://api.devrev.ai/code-changes.delete
Content-Type: application/json
```

Deletes a code change object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/code-changes.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.codeChanges.delete({
    id: "id"
});

```