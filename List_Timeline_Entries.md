# List Timeline Entries

```http
GET https://api.devrev.ai/timeline-entries.list
```

Lists the timeline entries for an object.



## Query Parameters

- Object (required): The ID of the object to list timeline entries for.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of entries to return. If not set, then this
defaults to `50`.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Visibility (optional): The visibility of the timeline entries to filter for. Note this is a
strict filter, such that only entries with the exact visibilities
specified will be returned.


## Response Body

- 200: The response to listing timeline entries for an object.

## Examples

```shell
curl -G https://api.devrev.ai/timeline-entries.list \
     -H "Authorization: Bearer <token>" \
     -d object=object \
     -d mode=after
```