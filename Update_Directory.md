# Update Directory

```http
POST https://api.devrev.ai/directories.update
Content-Type: application/json
```

Updates the specified directory.



## Response Body

- 200: Update directory response.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "reorder": {},
  "tags": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesUpdate({
    id: "id"
});

```