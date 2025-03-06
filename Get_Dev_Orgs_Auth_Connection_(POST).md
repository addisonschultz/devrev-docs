# Get Dev Orgs Auth Connection (POST)

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.get
Content-Type: application/json
```

Retrieves the details for an authentication connection.



## Response Body

- 200: Response object encapsulating the configuration details of an
authentication connection.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```