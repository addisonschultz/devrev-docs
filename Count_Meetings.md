# Count Meetings

```http
GET https://api.devrev.ai/meetings.count
```

Counts the meeting records.



## Query Parameters

- Channel (optional): Filters for meeting on specified channels.
- CreatedBy (optional): Filters for meetings created by the specified user(s).
- CustomFields (optional): Filters for meeting on custom fields.
- ExternalRef (optional): Filters for meetings with the provided external_ref(s).
- LinksLinkType (optional): Filters for link type in links associated with the meeting.

- LinksTarget (optional): Filters for target id in links associated with the meeting.

- LinksTargetObjectType (optional): Filters for target object type in links associated with the meeting.

- Members (optional): Filter for meeting on specified Member Ids.
- Organizer (optional): Filter for meeting on specified organizers.
- Parent (optional): Filters for meetings with the provided parent.
- State (optional): Filters for meeting on specified state or outcomes.
- Tags (optional): Filters for meeting by tags.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/meetings.count \
     -H "Authorization: Bearer <token>"
```