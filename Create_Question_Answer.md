# Create Question Answer

```http
POST https://api.devrev.ai/question-answers.create
Content-Type: application/json
```

Creates a question-answer.



## Response Body

- 201: Create question-answer response.

## Examples

```shell
curl -X POST https://api.devrev.ai/question-answers.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "access_level": "external",
  "answer": "answer",
  "applies_to_parts": [
    "applies_to_parts",
    "applies_to_parts"
  ],
  "owned_by": [
    "owned_by",
    "owned_by"
  ],
  "question": "question",
  "status": "archived"
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.questionAnswers.createQuestionAnswer({
    answer: "answer",
    appliesToParts: ["PROD-12345"],
    ownedBy: ["DEVU-12345"],
    question: "question",
    status: DevRev.QuestionAnswerStatus.Archived
});

```