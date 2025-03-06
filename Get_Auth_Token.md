# Get Auth Token

```http
GET https://api.devrev.ai/auth-tokens.get
```

Gets the token metadata corresponding to the given token ID under the
given Dev organization.




## Query Parameters

- TokenId (required): The unique identifier of the token under a given Dev organization.


## Response Body

- 200: The response to get the token metadata.

## Examples

```shell
curl -G https://api.devrev.ai/auth-tokens.get \
     -H "Authorization: Bearer <token>" \
     -d token_id=token_id
```