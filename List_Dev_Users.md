# List Dev Users

```http
GET https://api.devrev.ai/dev-users.list
```

Lists users within your organization.



## Query Parameters

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Email (optional): Filters Dev users based on email addresses.
- ExternalIdentityId (optional): Unique ID of the user in the external source.
- ExternalIdentityIssuer (optional): Issuer of the external identity of the user.
- Limit (optional): The maximum number of Dev users to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- SortBy (optional): Fields to sort the Dev users by and the direction to sort them.

- State (optional): Filters Dev users based on state.

## Response Body

- 200: The response to listing the Dev users.

## Examples

```shell
curl -G https://api.devrev.ai/dev-users.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```