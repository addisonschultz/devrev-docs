# Create Link

```http
POST https://api.devrev.ai/links.create
Content-Type: application/json
```

Creates a link between two objects to indicate a relationship.




## Response Body

- 201: The response to creating a new link.

## Examples

```shell
curl -X POST https://api.devrev.ai/links.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "link_type": "custom_link",
  "source": "source",
  "target": "target"
}'
```