# List Question Answers (POST)

```http
POST https://api.devrev.ai/question-answers.list
Content-Type: application/json
```

Lists a collection of question-answers.



## Response Body

- 200: List question-answers response.

## Examples

```shell
curl -X POST https://api.devrev.ai/question-answers.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "mode": "after"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.questionAnswers.listQuestionAnswersPost();

```