# List Rev Orgs

```http
GET https://api.devrev.ai/rev-orgs.list
```

Gets the list of Rev organizations' information belonging to the
authenticated user's Dev Organization which the user is also authorized
to access.




## Query Parameters

- CreatedBy (optional): Filters by creator.
- CreatedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- CreatedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- DisplayName (optional): Array of display names of Rev orgs to be filtered.
- ExternalRef (optional): List of external refs to filter Rev organizations for.
- Limit (optional): The maximum number of Rev organizations to be retrieved per page.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedDateAfter (optional): Filters for objects created after the provided timestamp (inclusive).

- ModifiedDateBefore (optional): Filters for objects created before the provided timestamp
(inclusive).

- SortBy (optional): Fields to sort the Rev organizations by and the direction to sort
them.


## Response Body

- 200: The response to getting a list of Rev organizations' information.


## Examples

```shell
curl -G https://api.devrev.ai/rev-orgs.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```