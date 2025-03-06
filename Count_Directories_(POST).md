# Count Directories (POST)

```http
POST https://api.devrev.ai/directories.count
Content-Type: application/json
```

Get count of directories matching given filter.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/directories.count \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.directory.directoriesCountPost();

```