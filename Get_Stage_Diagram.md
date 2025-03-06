# Get Stage Diagram

```http
GET https://api.devrev.ai/stage-diagrams.get
```

Gets a stage diagram.



## Query Parameters

- Id (optional): The ID of the stage diagram to get.
- IsCustomLeafType (optional): Whether the leaf type corresponds to a custom object. Specify this
along with leaf_type to get the default custom object stage diagram.

- LeafType (optional): The leaf type. Should be specified to retrieve the default stage
diagram for the leaf type. If not provided, then id is used.


## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/stage-diagrams.get \
     -H "Authorization: Bearer <token>"
```