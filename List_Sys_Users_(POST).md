# List Sys Users (POST)

```http
POST https://api.devrev.ai/sys-users.list
Content-Type: application/json
```

Lists system users within your organization.



## Response Body

- 200: The response to listing the system users.

## Examples

```shell
curl -X POST https://api.devrev.ai/sys-users.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```