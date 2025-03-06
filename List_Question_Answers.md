# List Question Answers

```http
GET https://api.devrev.ai/question-answers.list
```

Lists a collection of question-answers.



## Query Parameters

- AppliesToArticles (optional): Filters for question-answer belonging to any of the provided
articles.

- AppliesToParts (optional): Filters for question-answer belonging to any of the provided parts.

- CreatedBy (optional): Filters for question-answers created by any of the provided users.

- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- Limit (optional): The maximum number of question-answers to return. The default is
'50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.

- OwnedBy (optional): Filters for question-answers owned by any of the provided users.


## Response Body

- 200: List question-answers response.

## Examples

```shell
curl -G https://api.devrev.ai/question-answers.list \
     -H "Authorization: Bearer <token>" \
     -d mode=after
```