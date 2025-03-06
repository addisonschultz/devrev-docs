# Apply Roles

```http
POST https://api.devrev.ai/roles.apply
Content-Type: application/json
```

Assigns or revokes roles of a principal.



## Response Body

- 200: The response to roles apply.

## Examples

```shell
curl -X POST https://api.devrev.ai/roles.apply \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "principal": "principal"
}'
```