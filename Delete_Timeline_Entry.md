# Delete Timeline Entry

```http
POST https://api.devrev.ai/timeline-entries.delete
Content-Type: application/json
```

Deletes an entry from an object's timeline.



## Response Body

- 200: The response to deleting a timeline entry from an object.

## Examples

```shell
curl -X POST https://api.devrev.ai/timeline-entries.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```