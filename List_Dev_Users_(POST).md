# List Dev Users (POST)

```http
POST https://api.devrev.ai/dev-users.list
Content-Type: application/json
```

Lists users within your organization.



## Response Body

- 200: The response to listing the Dev users.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "mode": "after",
  "modified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  }
}'
```