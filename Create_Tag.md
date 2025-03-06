# Create Tag

```http
POST https://api.devrev.ai/tags.create
Content-Type: application/json
```

Creates a new tag, which is used to create associations between objects
and a logical concept denoted by the tag's name.




## Response Body

- 201: The response to creating a new tag.

## Examples

```shell
curl -X POST https://api.devrev.ai/tags.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "name": "name"
}'
```