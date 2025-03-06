# Get Schemas Stock

```http
GET https://api.devrev.ai/schemas.stock.get
```

Gets a stock schema fragment.



## Query Parameters

- Id (optional): The ID of the stock schema fragment.
- LeafType (optional): The leaf type this fragment applies to.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/schemas.stock.get \
     -H "Authorization: Bearer <token>"
```