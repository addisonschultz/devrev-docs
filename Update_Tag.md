# Update Tag

```http
POST https://api.devrev.ai/tags.update
Content-Type: application/json
```

Updates a tag's information.



## Response Body

- 200: The response for updating a tag.

## Examples

```shell
curl -X POST https://api.devrev.ai/tags.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "allowed_values": {},
  "id": "id"
}'
```