# Create Rev User

```http
POST https://api.devrev.ai/rev-users.create
Content-Type: application/json
```

Creates a Rev user for a Rev organization. Rev user can be a customer
or a lead of an organization.




## Response Body

- 201: Response object for creating a new Rev user for Rev organization.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {}
}'
```