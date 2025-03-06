# Create Group

```http
POST https://api.devrev.ai/groups.create
Content-Type: application/json
```

Creates a new group. A group is a collection of users.



## Response Body

- 201: The response to group creation.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "dynamic",
  "description": "description",
  "dynamic_group_info": {},
  "member_type": "dev_user",
  "name": "name"
}'
```