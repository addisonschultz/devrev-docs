# Create Stage Diagram

```http
POST https://api.devrev.ai/stage-diagrams.create
Content-Type: application/json
```

Creates a stage diagram.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/stage-diagrams.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "leaf_type": "leaf_type",
  "name": "name",
  "stages": [
    {
      "stage_id": "stage_id"
    },
    {
      "stage_id": "stage_id"
    }
  ]
}'
```