# Remove Rev Users Associations

```http
POST https://api.devrev.ai/rev-users.associations.remove
Content-Type: application/json
```

Removes an association from a Rev user. This API is only available when
the multi-association contact feature is enabled.




## Response Body

- 204: Response for removing associations from a Rev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.associations.remove \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "associations": [
    "associations",
    "associations"
  ],
  "rev_user_id": "rev_user_id"
}'
```