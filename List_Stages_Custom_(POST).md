# List Stages Custom (POST)

```http
POST https://api.devrev.ai/stages.custom.list
Content-Type: application/json
```

Lists custom stages.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stages.custom.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStagesListPost();

```