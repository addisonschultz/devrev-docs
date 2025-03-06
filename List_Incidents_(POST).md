# List Incidents (POST)

```http
POST https://api.devrev.ai/incidents.list
Content-Type: application/json
```

Lists incidents.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "acknowledged_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "actual_close_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "created_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "identified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "mitigated_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "mode": "after",
  "modified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "target_close_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.operate.incidentsListPost();

```