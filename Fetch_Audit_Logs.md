# Fetch Audit Logs

```http
POST https://api.devrev.ai/audit-logs.fetch
Content-Type: application/json
```

Retrieves audit logs.



## Response Body

- 200: Response for the audit logs export request. Response is empty as the
process is asynchronous. Upon completion, the user will be notified.


## Examples

```shell
curl -X POST https://api.devrev.ai/audit-logs.fetch \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "from": "from",
  "to": "to"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.compliance.exportAuditLogs({
    from: new Date("2023-01-01T12:00:00.000Z"),
    to: new Date("2023-01-01T12:00:00.000Z")
});

```