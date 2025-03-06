# Update Link Types Custom

```http
POST https://api.devrev.ai/link-types.custom.update
Content-Type: application/json
```

Updates a custom link type.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/link-types.custom.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "source_types": {
    "link_descriptors": [
      {},
      {}
    ]
  },
  "target_types": {
    "link_descriptors": [
      {},
      {}
    ]
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customLinkTypeUpdate({
    id: "id"
});

```