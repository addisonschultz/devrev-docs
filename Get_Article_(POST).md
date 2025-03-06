# Get Article (POST)

```http
POST https://api.devrev.ai/articles.get
Content-Type: application/json
```

Gets an article.



## Response Body

- 200: Get article response.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```