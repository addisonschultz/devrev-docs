# List Surveys

```http
GET https://api.devrev.ai/surveys.list
```

List surveys requested by the user.



## Query Parameters

- CreatedBy (optional): Filters for surveys created by any of these users.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of surveys to return. If not set, then the default
is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Name (optional): Filters for surveys by name(s).
- SortBy (optional): Fields to sort the surveys by and the direction to sort them.


## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/surveys.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```