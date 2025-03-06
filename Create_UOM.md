# Create UOM

```http
POST https://api.devrev.ai/uoms.create
Content-Type: application/json
```

Creates a Unit of Measurement on a part.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/uoms.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "aggregation_detail": {
    "aggregation_type": "duration"
  },
  "metric_name": "x",
  "name": "name",
  "product_id": "product_id",
  "unit": {
    "type": "boolean",
    "name": "name"
  }
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.uomsCreate({
    aggregationDetail: {
        aggregationType: DevRev.AggregationDetailAggregationType.Duration
    },
    metricName: "metric_name",
    name: "name",
    productId: "PROD-12345",
    unit: {
        type: DevRev.UnitType.Boolean,
        name: "name"
    }
});

```