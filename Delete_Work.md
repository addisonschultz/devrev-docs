# Delete Work

```http
POST https://api.devrev.ai/works.delete
Content-Type: application/json
```

Deletes a work item.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/works.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```