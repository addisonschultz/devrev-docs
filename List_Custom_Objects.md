# List Custom Objects

```http
GET https://api.devrev.ai/custom-objects.list
```

Lists custom objects.



## Query Parameters

- LeafType (required): Leaf type to filter.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Filter (optional): List of filters to apply.
- Limit (optional): The maximum number of items.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: The response to listing all custom objects matching the filter
criteria.


## Examples

```shell
curl -G https://api.devrev.ai/custom-objects.list \
     -H "Authorization: Bearer <token>" \
     -d leaf_type=leaf_type \
     -d mode=after
```