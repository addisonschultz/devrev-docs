# Get Dev Org (POST)

```http
POST https://api.devrev.ai/dev-orgs.get
Content-Type: application/json
```

Gets the Dev organization's information of the authenticated user.




## Response Body

- 200: The response to get a Dev organization's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/dev-orgs.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```