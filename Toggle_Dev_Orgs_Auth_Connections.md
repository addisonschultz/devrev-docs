# Toggle Dev Orgs Auth Connections

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.toggle
Content-Type: application/json
```

Enable or disable an authentication connection for a Dev organization.
Currently, only 1 authentication connection can be enabled at a time.
When a new authentication connection is enabled, the connection which
is currently enabled for the Dev organization is automatically
disabled.




## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.toggle \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id",
  "toggle": "disable"
}'
```