# List Links

```http
GET https://api.devrev.ai/links.list
```

Lists the available links.



## Query Parameters

- Object (required): The ID of the object to list the links for.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Direction (required): The direction of the links to list, otherwise if not present, then
links in both directions (source and target) are included.

- Limit (optional): The maximum number of links to return. If not set, then the default
is '50'.

- LinkType (optional): The link type(s) to filter for, otherwise if not present, all link
types are included.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ObjectTypes (optional): The object types to filter for, otherwise if not present, all object
types are included.

- Types (optional): The link types to filter for, otherwise if not present, all link
types are included.


## Response Body

- 200: The response to listing the links.

## Examples

```shell
curl -G https://api.devrev.ai/links.list \
     -H "Authorization: Bearer <token>" \
     -d object=object \
     -d direction=is_source \
     -d mode=after
```