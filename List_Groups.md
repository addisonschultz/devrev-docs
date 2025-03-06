# List Groups

```http
GET https://api.devrev.ai/groups.list
```

Lists the available groups.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- GroupType (optional): Filters the groups based on the group type.
- IngestionSource (optional): Filter groups by ingestion source(s).
- IsDefault (optional): Whether to fetch default or custom groups.
- Limit (optional): The maximum number of groups to return. The default is '50'.

- MemberType (optional): Filters the groups on basis of member type.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SortBy (optional): Comma-separated fields to sort the groups by.

## Response Body

- 200: The response to listing the groups.

## Examples

```shell
curl -G https://api.devrev.ai/groups.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```