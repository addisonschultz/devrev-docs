# Update Question Answer

```http
POST https://api.devrev.ai/question-answers.update
Content-Type: application/json
```

Updates a question-answer.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/question-answers.update \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "access_level": "external",
  "applies_to_articles": {},
  "applies_to_parts": {},
  "id": "id",
  "owned_by": {},
  "shared_with": {},
  "sources": {},
  "status": "archived",
  "tags": {}
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.questionAnswers.updateQuestionAnswer({
    id: "id"
});

```