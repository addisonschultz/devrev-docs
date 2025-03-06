# List Tags

```http
GET https://api.devrev.ai/tags.list
```

Lists the available tags.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of tags to return. The default is '50'.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Name (optional): Filters for tags with the provided names.
- SortBy (optional): Fields to sort tags by and the direction to sort them.

## Response Body

- 200: The response to listing the tags.

## Examples

```shell
curl -G https://api.devrev.ai/tags.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```