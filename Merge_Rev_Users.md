# Merge Rev Users

```http
POST https://api.devrev.ai/rev-users.merge
Content-Type: application/json
```

Merges the secondary Rev user into the primary Rev user.



## Response Body

- 200: Acknowledgment response indicating that the merge request has been
received for processing asynchronously.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.merge \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "primary_user": "primary_user",
  "secondary_user": "secondary_user"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.revUsers.merge({
    primaryUser: "primary_user",
    secondaryUser: "secondary_user"
});

```