# List Sla Trackers

```http
GET https://api.devrev.ai/sla-trackers.list
```

Lists SLA trackers matching a filter.



## Query Parameters

- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of SLA trackers to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- SortBy (optional): Fields to sort the SLA Trackers by and the direction to sort them.

- Stage (optional): The SLA tracker stages the filter matches.
- Status (optional): The SLA tracker statuses the filter matches.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/sla-trackers.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```