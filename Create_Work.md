# Create Work

```http
POST https://api.devrev.ai/works.create
Content-Type: application/json
```

Creates new work ([issue](https://devrev.ai/docs/product/build),
[ticket](https://devrev.ai/docs/product/support)) item.
[task](https://devrev.ai/docs/product/tasks) and opportunity work types
are supported in the beta version.




## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/works.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "issue",
  "priority": "p0"
}'
```