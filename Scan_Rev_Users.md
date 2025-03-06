# Scan Rev Users

```http
GET https://api.devrev.ai/rev-users.scan
```

Scans through all Rev users.



## Query Parameters

- Associations (optional): Filters for Rev users with specified associations
(account/workspace).

- CreatedBy (optional): Filters for Rev users that were created by the specified user(s).

- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- Cursor (optional): The cursor to resume iteration, otherwise the beginning if not
provided.

- CustomFields (optional): Filters for custom fields.
- Email (optional): List of emails of Rev users to be filtered.
- ExternalRef (optional): List of external refs to filter Rev users for.
- ExternalRefs (optional): Filters for Rev users with the provided external_refs.
- IsVerified (optional): Value of is_verified field to filter the Rev users.
- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- PhoneNumbers (optional): List of phone numbers, in E.164 format, to filter Rev users on.

- RevOrg (optional): List of IDs of Rev organizations to be filtered.
- Tags (optional): List of tags to be filtered.

## Response Body

- 200: The response to scanning Rev users.

## Examples

```shell
curl https://api.devrev.ai/rev-users.scan \
     -H "Authorization: Bearer <token>"
```