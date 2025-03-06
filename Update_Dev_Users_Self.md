# Update Dev Users Self

```http
POST https://api.devrev.ai/dev-users.self.update
Content-Type: application/json
```

Updates the authenticated user.



## Response Body

- 200: The response to update a Dev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.self.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "job_title": "customer_success_manager"
}'
```