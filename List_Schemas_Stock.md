# List Schemas Stock

```http
GET https://api.devrev.ai/schemas.stock.list
```

Lists stock schema fragments.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- FilterPreset (required): Filter preset to specify whether to filter only customization enabled
leaf types.

- LeafType (optional): The list of leaf types.
- Limit (optional): The maximum number of items.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Prune (optional): List of fields which are not required in the payload and can be
pruned away.

- SortBy (optional): The list of fields to sort the items by and how to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/schemas.stock.list \
     -H "Authorization: Bearer <token>" \
     -d filter_preset=customizable_types_preset \
     -d mode=after
```