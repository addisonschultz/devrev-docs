# List Link Types Custom

```http
GET https://api.devrev.ai/link-types.custom.list
```

Lists custom link types.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Deprecated (optional): Whether only deprecated link types should be filtered.
- Limit (optional): The maximum number of items.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Name (optional): The list of link type names.
- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/link-types.custom.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```