# Get Question Answer (POST)

```http
POST https://api.devrev.ai/question-answers.get
Content-Type: application/json
```

Gets a question-answer.



## Response Body

- 200: Get question-answer response.

## Examples

```shell
curl -X POST https://api.devrev.ai/question-answers.get \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.questionAnswers.getQuestionAnswerPost({
    id: "id"
});

```