# Delete Directory

```http
POST https://api.devrev.ai/directories.delete
Content-Type: application/json
```

Delete the specified directory.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesDelete({
    id: "id"
});

```