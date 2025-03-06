# Get Timeline Entry (POST)

```http
POST https://api.devrev.ai/timeline-entries.get
Content-Type: application/json
```

Gets an entry on an object's timeline.



## Response Body

- 200: The request to getting a timeline entry.

## Examples

```shell
curl -X POST https://api.devrev.ai/timeline-entries.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```