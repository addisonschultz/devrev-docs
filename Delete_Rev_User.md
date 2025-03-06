# Delete Rev User

```http
POST https://api.devrev.ai/rev-users.delete
Content-Type: application/json
```

Deletes a Rev user.



## Response Body

- 200: The response to deleting a Rev user of a Rev organization.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```