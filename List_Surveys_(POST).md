# List Surveys (POST)

```http
POST https://api.devrev.ai/surveys.list
Content-Type: application/json
```

List surveys requested by the user.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "mode": "after",
  "modified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.listPost();

```