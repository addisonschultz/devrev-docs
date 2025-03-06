# Get Schemas Aggregated

```http
GET https://api.devrev.ai/schemas.aggregated.get
```

Gets the aggregated schema.



## Query Parameters

- CustomSchemaFragmentIds (required): The list of custom schema fragment DONs which are to be aggregated.

- IsCustomLeafType (optional): Whether the leaf type corresponds to a custom object.
- LeafType (optional): The leaf type. Used for inferring the default stage diagram and
tenant fragment ID.

- StockSchemaFragmentId (optional): The stock schema fragment which is to be aggregated.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/schemas.aggregated.get \
     -H "Authorization: Bearer <token>" \
     -d "custom_schema_fragment_ids[]"=custom_schema_fragment_ids \
     -d "custom_schema_fragment_ids[]"=custom_schema_fragment_ids
```