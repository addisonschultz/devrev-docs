# List Articles

```http
GET https://api.devrev.ai/articles.list
```

Lists a collection of articles.



## Query Parameters

- AppliesToParts (optional): Filters for articles belonging to any of the provided parts.

- ArticleType (optional): Filter for the type of articles. If this is not provided, then
articles that are not content blocks are returned.

- AuthoredBy (optional): Filters for articles authored by any of the provided users.

- CreatedBy (optional): Filters for articles created by any of the provided users.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of articles to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- ModifiedBy (optional): Filters for articles modified by any of the provided users.

- OwnedBy (optional): Filters for articles owned by any of the provided users.
- Scope (optional): Filter for the scope of the articles.
- SharedWithMember (optional): ID of the group/member with whom the item is shared.
- SharedWithRole (optional): Role ID of the group/member with whom the item is shared.
- Tags (optional): Filters for article with any of the provided tags.

## Response Body

- 200: List articles response.

## Examples

```shell
curl -G https://api.devrev.ai/articles.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```