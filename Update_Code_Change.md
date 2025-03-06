# Update Code Change

```http
POST https://api.devrev.ai/code-changes.update
Content-Type: application/json
```

Updates a code change object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/code-changes.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.codeChanges.update({
    id: "id"
});

```