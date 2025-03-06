# List Dev Orgs Auth Connections

```http
GET https://api.devrev.ai/dev-orgs.auth-connections.list
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
curl https://api.devrev.ai/dev-orgs.auth-connections.list \
     -H "Authorization: Bearer <token>"
```