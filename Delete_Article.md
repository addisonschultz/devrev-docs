# Delete Article

```http
POST https://api.devrev.ai/articles.delete
Content-Type: application/json
```

Deletes an article.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```