# Ingest Metrics Devrev

```http
POST https://api.devrev.ai/metrics.devrev.ingest
Content-Type: application/json
```

Ingest endpoint for DevRev metrics data from clients.



## Examples

```shell
curl -X POST https://api.devrev.ai/metrics.devrev.ingest \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "metrics": [
    {
      "account_ref": "account_ref",
      "data_points": [
        {
          "timestamp": "timestamp",
          "value": 1.1
        },
        {
          "timestamp": "timestamp",
          "value": 1.1
        }
      ],
      "name": "name"
    },
    {
      "account_ref": "account_ref",
      "data_points": [
        {
          "timestamp": "timestamp",
          "value": 1.1
        },
        {
          "timestamp": "timestamp",
          "value": 1.1
        }
      ],
      "name": "name"
    }
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.productUsage.metricsDevrevIngest({
    metrics: [{
            accountRef: "account_ref",
            dataPoints: [{
                    timestamp: new Date("2023-01-01T12:00:00.000Z"),
                    value: 1.1
                }],
            name: "name"
        }]
});

```