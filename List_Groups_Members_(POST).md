# List Groups Members (POST)

```http
POST https://api.devrev.ai/groups.members.list
Content-Type: application/json
```

Lists the members in a group.



## Response Body

- 200: List of group members.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.members.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "group": "group",
  "mode": "after"
}'
```