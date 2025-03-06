# List Commands

```http
GET https://api.devrev.ai/commands.list
```

Lists commands for a Dev organization.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- ExecutorType (optional): Filtering based on executor_type.
- Limit (optional): The maximum number of commands to return per page. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Namespace (optional): Filter commands based on namespace.
- SortBy (optional): List of fields to sort the commands items by and how to sort them.

- SourceObjectId (optional): ID of the object where command is invoked (work/part/conversation).

- Status (optional): Filter commands based on status.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/commands.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```