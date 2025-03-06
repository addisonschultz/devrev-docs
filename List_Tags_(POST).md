# List Tags (POST)

```http
POST https://api.devrev.ai/tags.list
Content-Type: application/json
```

Lists the available tags.



## Response Body

- 200: The response to listing the tags.

## Examples

```shell
curl -X POST https://api.devrev.ai/tags.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```