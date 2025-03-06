# List Rev Orgs (POST)

```http
POST https://api.devrev.ai/rev-orgs.list
Content-Type: application/json
```

Gets the list of Rev organizations' information belonging to the
authenticated user's Dev Organization which the user is also authorized
to access.




## Response Body

- 200: The response to getting a list of Rev organizations' information.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-orgs.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "created_date": {},
  "mode": "after",
  "modified_date": {}
}'
```