# Create Link Types Custom

```http
POST https://api.devrev.ai/link-types.custom.create
Content-Type: application/json
```

Creates a custom link type.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/link-types.custom.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "backward_name": "backward_name",
  "forward_name": "forward_name",
  "name": "name",
  "source_types": [
    {},
    {}
  ],
  "target_types": [
    {},
    {}
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.customization.customLinkTypeCreate({
    backwardName: "backward_name",
    forwardName: "forward_name",
    name: "name",
    sourceTypes: [{
            "key": "value"
        }],
    targetTypes: [{
            "key": "value"
        }]
});

```