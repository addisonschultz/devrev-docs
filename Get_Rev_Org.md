# Get Rev Org

```http
GET https://api.devrev.ai/rev-orgs.get
```

Retrieves the Rev organization's information.



## Query Parameters

- Account (optional): The ID of account for which default Rev organization is to be
fetched.

- Id (optional): The ID of the required Rev organization.

## Response Body

- 200: The response to getting a Rev organization's information.

## Examples

```shell
curl https://api.devrev.ai/rev-orgs.get \
     -H "Authorization: Bearer <token>"
```