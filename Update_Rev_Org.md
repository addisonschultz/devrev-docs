# Update Rev Org

```http
POST https://api.devrev.ai/rev-orgs.update
Content-Type: application/json
```

Updates the Rev organization's information.



## Response Body

- 200: Response object to updating Rev organization's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-orgs.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "environment": "production",
  "id": "id"
}'
```