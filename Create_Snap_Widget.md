# Create Snap Widget

```http
POST https://api.devrev.ai/snap-widgets.create
Content-Type: application/json
```

Create a snap widget object.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/snap-widgets.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "email_preview"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.snapWidgets.create({
    type: "email_preview",
    rawEmailArtifact: "ARTIFACT-12345",
    sentTimestamp: new Date("2023-01-01T12:00:00.000Z")
});

```