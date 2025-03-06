# Get Metric Definition (POST)

```http
POST https://api.devrev.ai/metric-definitions.get
Content-Type: application/json
```

Gets a custom metric definition



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-definitions.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.slas.metricDefinitionsGetPost();

```