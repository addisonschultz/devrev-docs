# List Sys Users

```http
GET https://api.devrev.ai/sys-users.list
```

Lists system users within your organization.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of system users to return. Value can range from
'1' to '100', with a default of '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SortBy (optional): Fields to sort the system users by and the direction to sort them.


## Response Body

- 200: The response to listing the system users.

## Examples

```shell
curl -G https://api.devrev.ai/sys-users.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```