# Deactivate Dev Users

```http
POST https://api.devrev.ai/dev-users.deactivate
Content-Type: application/json
```

Deactivates the requested user.



## Response Body

- 200: The response to deactivate the Dev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.deactivate \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.devUsers.deactivate({
    id: "id"
});

```