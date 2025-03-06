# Delete Dev Orgs Auth Connection

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.delete
Content-Type: application/json
```

Deletes an authentication connection. Only enterprise connections which
are explicitly set up for a Dev organization can be deleted. Default
connections can not be deleted using this method.




## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```