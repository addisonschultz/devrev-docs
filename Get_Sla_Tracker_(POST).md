# Get Sla Tracker (POST)

```http
POST https://api.devrev.ai/sla-trackers.get
Content-Type: application/json
```

Gets an SLA tracker.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/sla-trackers.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```