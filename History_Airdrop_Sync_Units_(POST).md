# History Airdrop Sync Units (POST)

```http
POST https://api.devrev.ai/airdrop.sync-units.history
Content-Type: application/json
```

Gets a list of sync unit historical records.



## Response Body

- 200: List sync history response.

## Examples

```shell
curl -X POST https://api.devrev.ai/airdrop.sync-units.history \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "filter": {
    "ended_at": {
      "type": "preset",
      "preset_type": "last_n_days",
      "days": 4294967295
    }
  },
  "id": "id",
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.airdrop.syncUnitsHistoryPost({
    id: "id"
});

```