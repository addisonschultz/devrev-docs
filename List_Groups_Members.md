# List Groups Members

```http
GET https://api.devrev.ai/groups.members.list
```

Lists the members in a group.



## Query Parameters

- Group (required): ID of the group for which to list members.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of members to return. If not set, then the default
is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.


## Response Body

- 200: List of group members.

## Examples

```shell
curl -G https://api.devrev.ai/groups.members.list \
     -H "Authorization: Bearer <token>" \
     -d group=group \
     -d mode=after
```