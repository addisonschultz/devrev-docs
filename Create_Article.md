# Create Article

```http
POST https://api.devrev.ai/articles.create
Content-Type: application/json
```

Article is an object which can contain a URL or artifacts in the
resource. It also contains the data regarding the owner, author, status
and published date of the object. This call creates an article.




## Response Body

- 201: Create article response.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "access_level": "external",
  "applies_to_parts": [
    "applies_to_parts",
    "applies_to_parts"
  ],
  "article_type": "article",
  "custom_schema_spec": {},
  "owned_by": [
    "owned_by",
    "owned_by"
  ],
  "resource": {},
  "status": "archived",
  "title": "title"
}'
```