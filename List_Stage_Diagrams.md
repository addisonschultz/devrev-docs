# List Stage Diagrams

```http
GET https://api.devrev.ai/stage-diagrams.list
```

Lists stage diagrams.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from, otherwise if not provided, then
iteration starts from the beginning.

- IsCustomLeafType (optional): Whether only custom object stage diagrams should be filtered.

- LeafType (optional): The list of leaf types.
- Limit (optional): The maximum number of items.
- Name (optional): The list of stage diagram names.
- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/stage-diagrams.list \
     -H "Authorization: Bearer <token>"
```