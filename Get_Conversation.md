# Get Conversation

```http
GET https://api.devrev.ai/conversations.get
```

Gets the requested conversation's information.



## Query Parameters

- Id (required): The requested conversation's ID.

## Response Body

- 200: The response to getting a conversation's information.

## Examples

```shell
curl -G https://api.devrev.ai/conversations.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```