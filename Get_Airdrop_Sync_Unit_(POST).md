# Get Airdrop Sync Unit (POST)

```http
POST https://api.devrev.ai/airdrop.sync-units.get
Content-Type: application/json
```

Gets a single sync unit's information.



## Response Body

- 200: Response containing the requested sync unit.

## Examples

```shell
curl -X POST https://api.devrev.ai/airdrop.sync-units.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.airdrop.syncUnitsGetPost({
    id: "id"
});

```