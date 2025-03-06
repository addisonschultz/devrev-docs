# List Directories (POST)

```http
POST https://api.devrev.ai/directories.list
Content-Type: application/json
```

Lists directories matching the request.



## Response Body

- 200: List directory response.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesListPost();

```