# List Stages Custom

```http
GET https://api.devrev.ai/stages.custom.list
```

Lists custom stages.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from, otherwise if not provided, then
iteration starts from the beginning.

- Limit (optional): The maximum number of items.
- Name (optional): The list of stage names.
- Ordinal (optional): The list of stage ordinals.
- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/stages.custom.list \
     -H "Authorization: Bearer <token>"
```