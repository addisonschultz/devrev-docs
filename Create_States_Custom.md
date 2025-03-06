# Create States Custom

```http
POST https://api.devrev.ai/states.custom.create
Content-Type: application/json
```

Creates a custom state.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/states.custom.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "name": "name",
  "ordinal": 1
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customStatesCreate({
    name: "name",
    ordinal: 1
});

```