# Count Custom Objects

```http
GET https://api.devrev.ai/custom-objects.count
```

Counts custom objects.



## Query Parameters

- LeafType (required): Leaf type to filter.
- Filters (optional): List of filters to apply.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/custom-objects.count \
     -H "Authorization: Bearer <token>" \
     -d leaf_type=leaf_type
```