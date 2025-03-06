# Link Dev Users Identities

```http
POST https://api.devrev.ai/dev-users.identities.link
Content-Type: application/json
```

Links an external/secondary identity to the Dev user.



## Response Body

- 200: Response for the request to link an external identity to a Dev user.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.identities.link \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "dev_user": "dev_user",
  "id": "id",
  "issuer": "issuer"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.devUsers.identitiesLink({
    devUser: "dev_user",
    id: "id",
    issuer: "issuer"
});

```