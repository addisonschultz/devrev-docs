# Get Dev Orgs Auth Connection

```http
GET https://api.devrev.ai/dev-orgs.auth-connections.get
```

Retrieves the details for an authentication connection.



## Query Parameters

- Id (required): ID of the authentication connection.

## Response Body

- 200: Response object encapsulating the configuration details of an
authentication connection.


## Examples

```shell
curl -G https://api.devrev.ai/dev-orgs.auth-connections.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```