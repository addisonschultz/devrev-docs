# Get Metric Definition

```http
GET https://api.devrev.ai/metric-definitions.get
```

Gets a custom metric definition



## Query Parameters

- Id (optional): The ID of the metric definition to get.
- Name (optional): The unique human readable name of the metric.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/metric-definitions.get \
     -H "Authorization: Bearer <token>"
```