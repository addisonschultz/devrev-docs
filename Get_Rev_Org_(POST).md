# Get Rev Org (POST)

```http
POST https://api.devrev.ai/rev-orgs.get
Content-Type: application/json
```

Retrieves the Rev organization's information.



## Response Body

- 200: The response to getting a Rev organization's information.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-orgs.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```