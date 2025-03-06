# Update Group

```http
POST https://api.devrev.ai/groups.update
Content-Type: application/json
```

Updates the requested group.



## Response Body

- 200: The response to group update.

## Examples

```shell
curl -X POST https://api.devrev.ai/groups.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "dynamic_group_info": {
    "membership_expression": {
      "type": "and",
      "expressions": [
        {
          "type": "and",
          "expressions": [
            {
              "type": "and",
              "expressions": [
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                },
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                }
              ]
            },
            {
              "type": "and",
              "expressions": [
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                },
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                }
              ]
            }
          ]
        },
        {
          "type": "and",
          "expressions": [
            {
              "type": "and",
              "expressions": [
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                },
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                }
              ]
            },
            {
              "type": "and",
              "expressions": [
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                },
                {
                  "type": "and",
                  "expressions": [
                    {
                      "type": "primitive"
                    },
                    {
                      "type": "primitive"
                    }
                  ]
                }
              ]
            }
          ]
        }
      ]
    }
  },
  "id": "id"
}'
```