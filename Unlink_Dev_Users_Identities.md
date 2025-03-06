# Unlink Dev Users Identities

```http
POST https://api.devrev.ai/dev-users.identities.unlink
Content-Type: application/json
```

Unlinks an external/secondary identity from the Dev user.



## Response Body

- 200: Response for the request to unlink an external identity from a Dev
user.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.identities.unlink \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "dev_user": "dev_user",
  "issuer": "issuer"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.devUsers.identitiesUnlink({
    devUser: "dev_user",
    issuer: "issuer"
});

```