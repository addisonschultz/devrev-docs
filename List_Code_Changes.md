# List Code Changes

```http
GET https://api.devrev.ai/code-changes.list
```

Lists code change objects.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of code change objects to return. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.


## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/code-changes.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```