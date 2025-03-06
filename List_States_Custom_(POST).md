# List States Custom (POST)

```http
POST https://api.devrev.ai/states.custom.list
Content-Type: application/json
```

Lists custom states.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/states.custom.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStatesListPost();

```