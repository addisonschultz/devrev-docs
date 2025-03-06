# List Schemas Subtypes (POST)

```http
POST https://api.devrev.ai/schemas.subtypes.list
Content-Type: application/json
```

Lists subtypes.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/schemas.subtypes.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.subtypesListPost();

```