# Hybrid Search

```http
GET https://api.devrev.ai/search.hybrid
```

Performs search, using a combination of syntactic and semantic search.




## Query Parameters

- Namespace (required): The hybrid namespace to search in.
- Query (required): The query string.
- Limit (optional): The maximum number of items to return in a page. The default is '10'.

- SemanticWeight (optional): The weightage for semantic search. Values between 0 and 1 are
accepted.


## Response Body

- 200: Hybrid search response.

## Examples

```shell
curl -G https://api.devrev.ai/search.hybrid \
     -H "Authorization: Bearer <token>" \
     -d namespace=account \
     -d query=x
```