# Get Account

```http
GET https://api.devrev.ai/accounts.get
```

Retrieves an account's information.



## Query Parameters

- Id (required): The ID of the account to be retrieved.

## Response Body

- 200: The returned account.

## Examples

```shell
curl -G https://api.devrev.ai/accounts.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```