# List Incidents

```http
GET https://api.devrev.ai/incidents.list
```

Lists incidents.



## Query Parameters

- AppliesToParts (optional): Filters for incidents that apply to any of the provided parts.

- CreatedBy (optional): Filters for incidents created by any of the provided users.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- CustomFields (optional): Filters for custom fields.
- Limit (optional): The maximum number of items.
- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- OwnedBy (optional): Filters for incidents owned by any of the provided users.
- Pia (optional): Filters for incidents with any of the provided PIAs.
- Playbooks (optional): Filters for incidents with any of the provided playbooks.
- RelatedDocs (optional): Filters for incidents with any of the provided related docs.

- ReportedBy (optional): Filters for incidents with any of the provided reporters.
- Severity (optional): Filters for incidents containing any of the provided severities.

- SortBy (optional): The list of fields to sort the items by and how to sort them.

- Source (optional): Filters for incidents with any of the provided sources.
- Stage (optional): Filters for incidents in any of the provided stages.
- Subtype (optional): Filters for incidents with any of the provided subtypes.
- Title (optional): Filters for incidents by the provided titles.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/incidents.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```