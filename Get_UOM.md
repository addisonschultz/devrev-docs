# Get UOM

```http
GET https://api.devrev.ai/uoms.get
```

Gets a Unit of Measurement.



## Query Parameters

- Id (required): The Unit of Measurement (UOM)'s DON.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/uoms.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```