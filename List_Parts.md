# List Parts

```http
GET https://api.devrev.ai/parts.list
```

Lists a collection of [parts](https://devrev.ai/docs/product/parts).




## Query Parameters

- CreatedBy (optional): Filters for parts created by any of these users.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of parts to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Name (optional): Filters for parts of the provided name(s).
- OwnedBy (optional): Filters for parts owned by any of these users.
- ParentPartLevel (optional): Number of levels to fetch the part hierarchy up to.
- ParentPartParts (optional): Part IDs to fetch the hierarchy for. Required if any parent_part.*
fields are provided.

- Tags (optional): Filters for part with any of the provided tags.
- Type (optional): Filters for parts of the provided type(s).

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/parts.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```