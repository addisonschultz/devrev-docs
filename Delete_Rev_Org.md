# Delete Rev Org

```http
POST https://api.devrev.ai/rev-orgs.delete
Content-Type: application/json
```

Deletes the Rev organization.



## Response Body

- 200: The response to deleting a Rev organization.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-orgs.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```