# Update Preference

```http
POST https://api.devrev.ai/preferences.update
Content-Type: application/json
```

Updates the preference for a particular object.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/preferences.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "user_preferences",
  "general_preferences": {
    "availability": {}
  }
}'
```