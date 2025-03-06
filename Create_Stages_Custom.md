# Create Stages Custom

```http
POST https://api.devrev.ai/stages.custom.create
Content-Type: application/json
```

Creates a custom stage.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stages.custom.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "name": "name",
  "ordinal": 1,
  "state": "state"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStagesCreate({
    name: "name",
    ordinal: 1,
    state: "state"
});

```