# Create Metric Definition

```http
POST https://api.devrev.ai/metric-definitions.create
Content-Type: application/json
```

Creates a custom metric definition



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-definitions.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "applies_to": [
    "conversation",
    "conversation"
  ],
  "name": "x"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.slas.metricDefinitionsCreate({
    appliesTo: [DevRev.MetricDefinitionAppliesTo.Conversation],
    name: "name"
});

```