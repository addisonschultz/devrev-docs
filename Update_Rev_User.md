# Update Rev User

```http
POST https://api.devrev.ai/rev-users.update
Content-Type: application/json
```

Updates a Rev user.



## Response Body

- 200: Updated Rev user object.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_fragments": {},
  "custom_schema_spec": {},
  "id": "id"
}'
```