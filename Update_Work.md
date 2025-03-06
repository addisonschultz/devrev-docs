# Update Work

```http
POST https://api.devrev.ai/works.update
Content-Type: application/json
```

Updates a work item's information.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/works.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "issue",
  "developed_with": {},
  "priority": "p0"
}'
```