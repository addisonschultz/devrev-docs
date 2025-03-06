# List Schemas Custom

```http
GET https://api.devrev.ai/schemas.custom.list
```

Lists custom schema fragments.



## Query Parameters

- App (optional): The list of app names.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Deprecated (optional): Whether only deprecated fragments should be filtered.
- IsCustomLeafType (optional): Whether the leaf type corresponds to a custom object
- LeafType (optional): The list of leaf types.
- Limit (optional): The maximum number of items.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Prune (optional): List of fields which are not required in the payload and can be
pruned away.

- SortBy (optional): The list of fields to sort the items by and how to sort them.

- Subtype (optional): The list of subtypes.
- Types (optional): Filters for custom schema fragment of the provided types.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/schemas.custom.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```