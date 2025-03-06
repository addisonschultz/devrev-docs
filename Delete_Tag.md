# Delete Tag

```http
POST https://api.devrev.ai/tags.delete
Content-Type: application/json
```

Deletes a tag.



## Response Body

- 200: The response for deleting a tag.

## Examples

```shell
curl -X POST https://api.devrev.ai/tags.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```