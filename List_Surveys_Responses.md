# List Surveys Responses

```http
GET https://api.devrev.ai/surveys.responses.list
```

List survey responses requested by the user.



## Query Parameters

- CreatedBy (optional): Filters for survey responses created by any of these users.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- DispatchIds (optional): Filters for survey responses associated with these unique IDs.

- Limit (optional): The maximum number of survey responses to return. If not set, then
the default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Objects (optional): Filters for survey responses created for the objects.
- Recipient (optional): Filters for survey responses dispatched to any of these users.

- SortBy (optional): Fields to sort the survey responses by and the direction to sort
them.

- Stages (optional): Filters for survey response stages.
- Surveys (optional): Filters for survey responses for the provided survey IDs.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/surveys.responses.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```