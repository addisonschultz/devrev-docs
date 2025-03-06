# List Engagements

```http
GET https://api.devrev.ai/engagements.list
```

Lists the engagement records.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- ExternalRef (optional): Filters for meetings with the provided external_refs.
- Limit (optional): The maximum number of engagements to return.
- Members (optional): Filters for engagement of the provided members.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Parent (optional): Filters for engagements with the provided parent.
- SortBy (optional): Fields to sort the engagements by and the direction to sort them.

- Type (optional): Filters for engagement of the provided types.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/engagements.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```