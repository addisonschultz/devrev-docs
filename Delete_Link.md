# Delete Link

```http
POST https://api.devrev.ai/links.delete
Content-Type: application/json
```

Deletes a link.



## Response Body

- 200: The response for deleting a link.

## Examples

```shell
curl -X POST https://api.devrev.ai/links.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```