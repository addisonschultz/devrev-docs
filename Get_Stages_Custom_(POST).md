# Get Stages Custom (POST)

```http
POST https://api.devrev.ai/stages.custom.get
Content-Type: application/json
```

Gets a custom stage.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stages.custom.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStagesGetPost({
    id: "id"
});

```