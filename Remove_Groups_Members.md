# Remove Groups Members

```http
POST https://api.devrev.ai/groups.members.remove
Content-Type: application/json
```

Removes a member from a group.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.members.remove \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "group": "group",
  "member": "member"
}'
```