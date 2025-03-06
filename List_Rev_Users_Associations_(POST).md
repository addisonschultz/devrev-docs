# List Rev Users Associations (POST)

```http
POST https://api.devrev.ai/rev-users.associations.list
Content-Type: application/json
```

Returns a list of associations on a Rev user.



## Response Body

- 200: The response to listing all the associations of a Rev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.associations.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "rev_user_id": "rev_user_id"
}'
```