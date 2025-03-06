# Create Dev User

```http
POST https://api.devrev.ai/dev-users.create
Content-Type: application/json
```

Creates a Dev user for a Dev organization.



## Response Body

- 201: Response object for request to create a new Dev user for a Dev
organization.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "email": "email",
  "state": "shadow"
}'
```