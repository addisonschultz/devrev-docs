# List Timeline Entries (POST)

```http
POST https://api.devrev.ai/timeline-entries.list
Content-Type: application/json
```

Lists the timeline entries for an object.



## Response Body

- 200: The response to listing timeline entries for an object.

## Examples

```shell
curl -X POST https://api.devrev.ai/timeline-entries.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "object": "object"
}'
```