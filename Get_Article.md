# Get Article

```http
GET https://api.devrev.ai/articles.get
```

Gets an article.



## Query Parameters

- Id (required): The ID of the required article.

## Response Body

- 200: Get article response.

## Examples

```shell
curl -G https://api.devrev.ai/articles.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```