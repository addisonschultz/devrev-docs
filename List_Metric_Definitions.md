# List Metric Definitions

```http
GET https://api.devrev.ai/metric-definitions.list
```

Lists metric definitions matching a filter.



## Query Parameters

- AppliesToType (optional): The type of objects the metric definition applies to.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- IncludeCustomMetrics (optional): Whether to include custom metrics in the response. If not set, then
custom metrics are excluded.

- Limit (optional): The maximum number of records to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SortBy (optional): Fields to sort the records by and the direction to sort them.

- Status (optional): The status of the metric definition.
- Type (optional): The type of metric definitions sought.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/metric-definitions.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```