# Get Preference (POST)

```http
POST https://api.devrev.ai/preferences.get
Content-Type: application/json
```

Get the preferences object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/preferences.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "user_preferences",
  "object": "object"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.preferences.getPost({
    type: "user_preferences",
    object: "DEV-AbCdEfGh"
});

```