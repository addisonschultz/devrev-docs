# List Reactions

```http
GET https://api.devrev.ai/reactions.list
```

Lists the reactors for an object.



## Query Parameters

- Emoji (required): The emoji to list the reactors for. This can be the short name of the
emoji (e.g. "joy"), or the code point (e.g. "1f602").

- Object (required): The ID of the object to list reactors for.
- Cursor (optional): The cursor to resume iteration from, otherwise if not provided, then
iteration starts from the beginning.

- Limit (optional): The maximum number of reactors to return.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/reactions.list \
     -H "Authorization: Bearer <token>" \
     -d emoji=emoji \
     -d object=object
```