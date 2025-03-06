# List Rev Users (POST)

```http
POST https://api.devrev.ai/rev-users.list
Content-Type: application/json
```

Returns a list of all Rev Users belonging to the authenticated user's
Dev organization.




## Response Body

- 200: The response to listing all Rev users matching the filter criteria.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {},
  "mode": "after",
  "modified_date": {}
}'
```