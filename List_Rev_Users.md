# List Rev Users

```http
GET https://api.devrev.ai/rev-users.list
```

Returns a list of all Rev Users belonging to the authenticated user's
Dev organization.




## Query Parameters

- Associations (optional): Filters for Rev users with specified associations
(account/workspace).

- CreatedBy (optional): Filters for Rev users that were created by the specified user(s).

- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Email (optional): List of emails of Rev users to be filtered.
- ExternalRef (optional): List of external refs to filter Rev users for.
- IsVerified (optional): Value of is_verified field to filter the Rev users.
- Limit (optional): The maximum number of Rev users to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- PhoneNumbers (optional): List of phone numbers, in E.164 format, to filter Rev users on.

- RevOrg (optional): List of IDs of Rev organizations to be filtered.
- SortBy (optional): Fields to sort the Rev users by and the direction to sort them.


## Response Body

- 200: The response to listing all Rev users matching the filter criteria.


## Examples

```shell
curl -G https://api.devrev.ai/rev-users.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```