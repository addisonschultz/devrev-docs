# List Content Template

```http
GET https://api.devrev.ai/content-template.list
```

Lists the content templates.



## Query Parameters

- CreatedBy (optional): Filters for content template created by any of these users.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of content template to return. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Name (optional): Filters for content template based on name.
- SortBy (optional): Fields to sort the content template by and the direction to sort
them.

- Type (optional): Filters for content template of the provided types.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/content-template.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```