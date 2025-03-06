# List Org Schedules

```http
GET https://api.devrev.ai/org-schedules.list
```

Gets list of organization schedules.



## Query Parameters

- CreatedById (optional): Creator ID the filter matches.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): Max number of organization schedules returned in a page. Default is
50.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Status (optional): The organization schedule statuses the filter matches.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/org-schedules.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```