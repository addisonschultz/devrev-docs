# Get Service Account

```http
GET https://api.devrev.ai/service-accounts.get
```

Gets a service account.



## Query Parameters

- Id (required): The ID of the requested service account.

## Response Body

- 200: The response object that carries the service account's information
corresponding to the request.


## Examples

```shell
curl -G https://api.devrev.ai/service-accounts.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```