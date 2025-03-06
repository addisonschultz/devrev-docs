# List UOMs

```http
GET https://api.devrev.ai/uoms.list
```

Gets the Unit of Measurements based on the given filters.



## Query Parameters

- AggregationTypes (optional): List of aggregation types for filtering list of UOMs.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Ids (optional): List of Unit of Measurement (UOM) DONs to be used in filtering
complete list of UOMs defined in a Dev Org.

- Limit (optional): The maximum number of UOMs to be returned in a response. The default
is '50'.

- MetricNames (optional): List of metric names for filtering list of UOMs.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- PartIds (optional): List of part IDs for filtering list of UOMs.
- ProductIds (optional): List of product IDs for filtering list of UOMs.
- SortBy (optional): Fields to sort the Unit Of Measuments (UOMs) by and the direction to
sort them.

- UnitTypes (optional): List of unit types for filtering list of UOMs.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/uoms.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```