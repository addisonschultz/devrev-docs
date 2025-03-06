# List Articles (POST)

```http
POST https://api.devrev.ai/articles.list
Content-Type: application/json
```

Lists a collection of articles.



## Response Body

- 200: List articles response.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```