# List Slas

```http
GET https://api.devrev.ai/slas.list
```

Lists SLAs matching a filter.



## Query Parameters

- AppliesTo (optional): The object types the SLA applies to.
- AppliesToOp (required): The Filter operator to be applied on the applies to object types
filter.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of SLAs to return. The default is '50'.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SlaType (optional): The SLA types the filter matches.
- SortBy (optional): Fields to sort the SLAs by and the direction to sort them.
- Status (optional): The SLA statuses the filter matches.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/slas.list \
     -H "Authorization: Bearer <token>" \
     -d applies_to_op=all \
     -d mode=after
```