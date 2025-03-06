# Unlink Rev Users

```http
POST https://api.devrev.ai/rev-users.unlink
Content-Type: application/json
```

Unlinks a rev user from a rev org.



## Response Body

- 200: Response for unlinking/removing a Rev user from a Rev organization.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.unlink \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.revUsers.unlinkRevUserFromRevOrg();

```