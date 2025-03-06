# Get Atom (POST)

```http
POST https://api.devrev.ai/atoms.get
Content-Type: application/json
```

Gets the specified object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/atoms.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```