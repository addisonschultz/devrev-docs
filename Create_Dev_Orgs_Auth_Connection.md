# Create Dev Orgs Auth Connection

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.create
Content-Type: application/json
```

Creates a new enterprise authentication connection for a Dev
organization. This authentication connection will not be enabled by
default for the organization and the user will need to explicitly
enable this. Keep in mind that at a time, only one authentication
connection can be enabled for a Dev organization. At present, only 5
enterprise connections can be created by an organization.




## Response Body

- 201: Response for the request to create a new enterprise authentication
connection.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "google_apps",
  "client_id": "client_id",
  "client_secret": "client_secret",
  "tenant_domain": "tenant_domain"
}'
```