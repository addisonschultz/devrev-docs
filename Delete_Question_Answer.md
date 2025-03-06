# Delete Question Answer

```http
POST https://api.devrev.ai/question-answers.delete
Content-Type: application/json
```

Deletes a question-answer.



## Examples

```shell
curl -X POST https://api.devrev.ai/question-answers.delete \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.questionAnswers.deleteQuestionAnswer({
    id: "id"
});

```