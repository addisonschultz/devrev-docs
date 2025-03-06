# Update Sys User

```http
POST https://api.devrev.ai/sys-users.update
Content-Type: application/json
```

Updates the system user.



## Response Body

- 200: Updated Sys user object.

## Examples

```shell
curl -X POST https://api.devrev.ai/sys-users.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```