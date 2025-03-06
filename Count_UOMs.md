# Count UOMs

```http
GET https://api.devrev.ai/uoms.count
```

Counts the number of Unit of Measurements based on the given filters.




## Query Parameters

- AggregationTypes (optional): List of aggregation types for filtering list of UOMs.
- Ids (optional): List of Unit of Measurement (UOM) DONs to be used in filtering
complete list of UOMs defined in a Dev Org.

- MetricNames (optional): List of metric names for filtering list of UOMs.
- PartIds (optional): List of part IDs for filtering list of UOMs.
- ProductIds (optional): List of product IDs for filtering list of UOMs.
- UnitTypes (optional): List of unit types for filtering list of UOMs.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/uoms.count \
     -H "Authorization: Bearer <token>"
```