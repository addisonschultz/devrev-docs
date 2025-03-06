# Group Incidents (POST)

```http
POST https://api.devrev.ai/incidents.group
Content-Type: application/json
```

Lists collections of incidents by groups.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/incidents.group \
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
  "group_by": "group_by",
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
await client.operate.incidentsGroupPost({
    groupBy: "group_by"
});

```