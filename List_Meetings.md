# List Meetings

```http
GET https://api.devrev.ai/meetings.list
```

Lists the meeting records.



## Query Parameters

- Channel (optional): Filters for meeting on specified channels.
- CreatedBy (optional): Filters for meetings created by the specified user(s).
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- CustomFields (optional): Filters for meeting on custom fields.
- ExternalRef (optional): Filters for meetings with the provided external_ref(s).
- Limit (optional): The maximum number of meetings to return.
- LinksLinkType (optional): Filters for link type in links associated with the meeting.

- LinksTarget (optional): Filters for target id in links associated with the meeting.

- LinksTargetObjectType (optional): Filters for target object type in links associated with the meeting.

- Members (optional): Filter for meeting on specified Member Ids.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Organizer (optional): Filter for meeting on specified organizers.
- Parent (optional): Filters for meetings with the provided parent.
- SortBy (optional): Fields to sort the meetings by and the direction to sort them.

- State (optional): Filters for meeting on specified state or outcomes.
- Tags (optional): Filters for meeting by tags.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/meetings.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```