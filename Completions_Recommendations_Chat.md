# Completions Recommendations Chat

```http
POST https://api.devrev.ai/recommendations.chat.completions
Content-Type: application/json
```

Returns a response for the chat conversation.



## Response Body

- 200: The response for the generated chat completion.

## Examples

```shell
curl -X POST https://api.devrev.ai/recommendations.chat.completions \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "messages": [
    {
      "content": "content",
      "role": "assistant"
    },
    {
      "content": "content",
      "role": "assistant"
    }
  ]
}'
```