# List Directories

```http
GET https://api.devrev.ai/directories.list
```

Lists directories matching the request.



## Query Parameters

- CreatedBy (optional): Filters for directories created by any of the provided users.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of directories to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedBy (optional): Filters for directories modified by any of the provided users.


## Response Body

- 200: List directory response.

## Examples

```shell
curl -G https://api.devrev.ai/directories.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```