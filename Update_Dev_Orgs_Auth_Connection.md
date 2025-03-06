# Update Dev Orgs Auth Connection

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.update
Content-Type: application/json
```

Updates an authentication connection.



## Response Body

- 201: Response for the request to update an enterprise authentication
connection.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "google_apps"
}'
```