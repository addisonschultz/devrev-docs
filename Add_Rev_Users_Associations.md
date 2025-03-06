# Add Rev Users Associations

```http
POST https://api.devrev.ai/rev-users.associations.add
Content-Type: application/json
```

Adds an association to a Rev user. This API is only available when the
multi-association contact feature is enabled.




## Response Body

- 201: Response for adding associations to a Rev user.

## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.associations.add \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "associations": [
    {},
    {}
  ],
  "rev_user_id": "rev_user_id"
}'
```