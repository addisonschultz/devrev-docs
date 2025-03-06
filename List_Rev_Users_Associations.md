# List Rev Users Associations

```http
GET https://api.devrev.ai/rev-users.associations.list
```

Returns a list of associations on a Rev user.



## Query Parameters

- RevUserId (required): The ID of Rev user to list all associations of.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of Associations to return per page. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.


## Response Body

- 200: The response to listing all the associations of a Rev user.

## Examples

```shell
curl -G https://api.devrev.ai/rev-users.associations.list \
     -H "Authorization: Bearer <token>" \
     -d rev_user_id=rev_user_id \
     -d mode=after
```