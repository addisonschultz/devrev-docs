# Activate Dev Users

```http
POST https://api.devrev.ai/dev-users.activate
Content-Type: application/json
```

Activates the requested user.



## Response Body

- 200: The response to activate the Dev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.activate \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.devUsers.activate({
    id: "id"
});

```