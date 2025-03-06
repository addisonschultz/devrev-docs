# List Link Types Custom (POST)

```http
POST https://api.devrev.ai/link-types.custom.list
Content-Type: application/json
```

Lists custom link types.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/link-types.custom.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
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
await client.customization.customLinkTypeListPost();

```