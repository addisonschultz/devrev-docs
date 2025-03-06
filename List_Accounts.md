# List Accounts

```http
GET https://api.devrev.ai/accounts.list
```

Gets a list of accounts.



## Query Parameters

- CreatedBy (optional): Filters for accounts created by the specified user(s).
- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- DisplayName (optional): Array of display names of accounts to be filtered.
- ExternalRefs (optional): Array of references of accounts to be filtered.
- Limit (optional): The maximum number of accounts to return per page. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- SortBy (optional): Fields to sort the accounts by and the direction to sort them in.

- Stage (optional): Filters for accounts on specified stages.
- Websites (optional): Array of websites of accounts to be filtered.

## Response Body

- 200: The response to listing all accounts matching the filter criteria.


## Examples

```shell
curl -G https://api.devrev.ai/accounts.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```