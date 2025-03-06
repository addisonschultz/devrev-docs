# Resources Snap Ins (POST)

```http
POST https://api.devrev.ai/snap-ins.resources
Content-Type: application/json
```

Gets snap-in resources for a user in a snap-in.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/snap-ins.resources \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "user": "user"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.snapIns.resourcesPost({
    id: "id",
    user: "user"
});

```