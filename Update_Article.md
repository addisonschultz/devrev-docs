# Update Article

```http
POST https://api.devrev.ai/articles.update
Content-Type: application/json
```

Updates an article.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/articles.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "access_level": "external",
  "aliases": {
    "set": [
      "set",
      "set"
    ]
  },
  "applies_to_parts": {},
  "artifacts": {},
  "authored_by": {},
  "content_blocks": {
    "set": [
      "set",
      "set"
    ]
  },
  "custom_schema_spec": {},
  "extracted_content": {},
  "id": "id",
  "owned_by": {},
  "reorder": {},
  "shared_with": {},
  "status": "archived",
  "tags": {}
}'
```