# List Dev Orgs Auth Connections (POST)

```http
POST https://api.devrev.ai/dev-orgs.auth-connections.list
Content-Type: application/json
```

Lists all the authentication connections available for a Dev
organization. This list will include both social and enterprise
connections which are either available by default or are explicitly
created by the user.




## Response Body

- 200: Response object for the request to list all the social and enterprise
authentication connections configured for a Dev organization.


## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.auth-connections.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```