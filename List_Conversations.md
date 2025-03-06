# List Conversations

```http
GET https://api.devrev.ai/conversations.list
```

Lists the available conversations.



## Query Parameters

- AppliesToParts (optional): Filters for conversations belonging to any of the provided parts.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Group (optional): Filters for conversation that belong to the given groups.
- IsCreatorVerified (optional): Filters for conversations that are created by verified users.

- IsFrozen (optional): Filters for conversations that are frozen.
- IsSpam (optional): Filters for conversations that are spam.
- Limit (optional): The maximum number of conversations to return. The default is '50'.

- Members (optional): Filters for conversations where these users are participants.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

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
- Tags (optional): Filters for conversations with any of the provided tags.
- TagsV2Id (optional): The ID of the tag.
- TagsV2Value (optional): The value for the object's association with the tag. If specified,
the value must be one that's specified in the tag's allowed values.


## Response Body

- 200: The response to listing the conversations.

## Examples

```shell
curl -G https://api.devrev.ai/conversations.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```