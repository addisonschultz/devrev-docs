# Core Search

```http
GET https://api.devrev.ai/search.core
```

Searches for records based on a given query.



## Query Parameters

- Query (required): The query string. Search query language:
https://docs.devrev.ai/product/search#fields

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of items to return in a page. The default is '10'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- Namespaces (optional): The namespaces to search in.
- SortBy (required): The property on which to sort the search results. The default is
RELEVANCE.

- SortOrder (required): Sorting order. The default is DESCENDING.

## Response Body

- 200: Search response.

## Examples

```shell
curl -G https://api.devrev.ai/search.core \
     -H "Authorization: Bearer <token>" \
     -d query=query \
     -d mode=after \
     -d sort_by=created_date \
     -d sort_order=asc
```