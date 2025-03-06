# Count Articles

```http
GET https://api.devrev.ai/articles.count
```

Get count of articles matching given filter.



## Query Parameters

- Ancestor (optional): The ancestor directory of the articles.
- AppliesToParts (optional): Filters for articles belonging to any of the provided parts.

- ArticleType (optional): Filter for the type of articles. If this is not provided, then
articles that are not content blocks are returned.

- AuthoredBy (optional): Filters for articles authored by any of the provided users.

- CreatedBy (optional): Filters for articles created by any of the provided users.
- ModifiedBy (optional): Filters for articles modified by any of the provided users.

- OwnedBy (optional): Filters for articles owned by any of the provided users.
- Scope (optional): Filter for the scope of the articles.
- SharedWithMember (optional): ID of the group/member with whom the item is shared.
- SharedWithRole (optional): Role ID of the group/member with whom the item is shared.
- Tags (optional): Filters for article with any of the provided tags.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/articles.count \
     -H "Authorization: Bearer <token>"
```