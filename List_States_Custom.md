# List States Custom

```http
GET https://api.devrev.ai/states.custom.list
```

Lists custom states.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from, otherwise if not provided, then
iteration starts from the beginning.

- IsFinal (optional): Whether only final states should be filtered.
- Limit (optional): The maximum number of items.
- Name (optional): The list of state names.
- Ordinal (optional): The list of state ordinals.
- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/states.custom.list \
     -H "Authorization: Bearer <token>"
```