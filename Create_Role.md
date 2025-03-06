# Create Role

```http
POST https://api.devrev.ai/roles.create
Content-Type: application/json
```

Creates a new role.



## Response Body

- 201: A response to a request to create a new role.

## Examples

```shell
curl -X POST https://api.devrev.ai/roles.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "target": "article"
}'
```