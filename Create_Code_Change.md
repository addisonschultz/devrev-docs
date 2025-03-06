# Create Code Change

```http
POST https://api.devrev.ai/code-changes.create
Content-Type: application/json
```

Creates a code change object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/code-changes.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.codeChanges.create();

```