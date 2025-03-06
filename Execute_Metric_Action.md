# Execute Metric Action

```http
POST https://api.devrev.ai/metric-action.execute
Content-Type: application/json
```

Executes the metric action on the given object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/metric-action.execute \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "action": "complete",
  "event_date": "event_date",
  "metric": "metric",
  "object": "object"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.slas.metricActionExecute({
    action: DevRev.MetricActionExecuteRequestAction.Complete,
    eventDate: new Date("2023-01-01T12:00:00.000Z"),
    metric: "metric",
    object: "object"
});

```