# Create Directory

```http
POST https://api.devrev.ai/directories.create
Content-Type: application/json
```

Creates a directory for the specified inputs.



## Response Body

- 201: Create directory response.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "title": "title"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesCreate({
    title: "title"
});

```