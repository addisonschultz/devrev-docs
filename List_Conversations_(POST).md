# List Conversations (POST)

```http
POST https://api.devrev.ai/conversations.list
Content-Type: application/json
```

Lists the available conversations.



## Response Body

- 200: The response to listing the conversations.

## Examples

```shell
curl -X POST https://api.devrev.ai/conversations.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after",
  "modified_date": {},
  "sla_summary": {
    "target_time": {
      "type": "preset",
      "preset_type": "last_n_days",
      "days": 4294967295
    }
  },
  "stage": {}
}'
```