# Add Groups Members

```http
POST https://api.devrev.ai/groups.members.add
Content-Type: application/json
```

Adds a member to a group.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.members.add \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "group": "group",
  "member": "member"
}'
```