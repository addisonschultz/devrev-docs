# Get Directory (POST)

```http
POST https://api.devrev.ai/directories.get
Content-Type: application/json
```

Gets the specified directory.



## Response Body

- 200: Get directory response.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesGetPost({
    id: "id"
});

```