# Update Dev User

```http
POST https://api.devrev.ai/dev-users.update
Content-Type: application/json
```

Updates the user corresponding to the input Id.



## Response Body

- 200: The response to update a Dev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-users.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "custom_schema_spec": {},
  "id": "id",
  "job_title": "customer_success_manager"
}'
```