# Export Accounts

```http
GET https://api.devrev.ai/accounts.export
```

Exports a collection of accounts.



## Query Parameters

- CreatedBy (optional): Filters for accounts created by the specified user(s).
- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- DisplayName (optional): Array of display names of accounts to be filtered.
- ExternalRefs (optional): Array of references of accounts to be filtered.
- First (optional): The number of accounts to return. The default is '50'.
- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- SortBy (optional): Fields to sort the accounts by and the direction to sort them in.

- Stage (optional): Filters for accounts on specified stages.
- Websites (optional): Array of websites of accounts to be filtered.

## Response Body

- 200: The response to exporting a collection of accounts.

## Examples

```shell
curl https://api.devrev.ai/accounts.export \
     -H "Authorization: Bearer <token>"
```