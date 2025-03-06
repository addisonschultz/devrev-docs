# Update Timeline Entry

```http
POST https://api.devrev.ai/timeline-entries.update
Content-Type: application/json
```

Updates an entry on an object's timeline.



## Response Body

- 200: The response to updating a timeline entry.

## Examples

```shell
curl -X POST https://api.devrev.ai/timeline-entries.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "timeline_comment",
  "artifacts": {},
  "body_type": "data",
  "snap_kit_body": {}
}'
```