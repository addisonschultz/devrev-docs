# Get Custom Object (POST)

```http
POST https://api.devrev.ai/custom-objects.get
Content-Type: application/json
```

Gets a custom object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/custom-objects.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customObjectsGetPost();

```