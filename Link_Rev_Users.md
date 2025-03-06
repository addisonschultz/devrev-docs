# Link Rev Users

```http
POST https://api.devrev.ai/rev-users.link
Content-Type: application/json
```

Links a rev user to a rev org.



## Response Body

- 200: Response for linking a Rev user to an existing Rev organization.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.link \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.revUsers.linkRevUserToRevOrg();

```