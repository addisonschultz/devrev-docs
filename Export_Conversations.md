# Export Conversations

```http
GET https://api.devrev.ai/conversations.export
```

Exports a collection of conversation items.



## Query Parameters

- AppliesToParts (optional): Filters for conversations belonging to any of the provided parts.

- CustomFields (optional): Filters for custom fields.
- First (optional): The number of conversation items to return. The default is '50', the
maximum is '5000'.

- Group (optional): Filters for conversation that belong to the given groups.
- IsCreatorVerified (optional): Filters for conversations that are created by verified users.

- IsFrozen (optional): Filters for conversations that are frozen.
- IsSpam (optional): Filters for conversations that are spam.
- Members (optional): Filters for conversations where these users are participants.

- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- OwnedBy (optional): Filters for conversations owned by any of these users.
- RevOrg (optional): Filters for conversations that are associated with any of the
provided Rev organizations.

- RevOrgs (optional): Filters for conversations that are associated with any of the
provided Rev organizations.

- SlaSummaryStage (optional): Filters for records with any of the provided SLA stages.
- SourceChannel (optional): Filters for conversations with any of the provided source channels.

- SourceChannels (optional): Filters for conversations with any of the provided source channels.

- StageName (optional): Filters for records in the provided stage(s) by name.
- Subtype (optional): Filters for conversation with any of the provided subtypes.

- Tags (optional): Filters for conversations with any of the provided tags.
- TagsV2Id (optional): The ID of the tag.
- TagsV2Value (optional): The value for the object's association with the tag. If specified,
the value must be one that's specified in the tag's allowed values.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/conversations.export \
     -H "Authorization: Bearer <token>"
```