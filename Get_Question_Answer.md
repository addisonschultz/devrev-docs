# Get Question Answer

```http
GET https://api.devrev.ai/question-answers.get
```

Gets a question-answer.



## Query Parameters

- Id (required): The ID of the required question-answer.

## Response Body

- 200: Get question-answer response.

## Examples

```shell
curl -G https://api.devrev.ai/question-answers.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```