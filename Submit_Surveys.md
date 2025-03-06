# Submit Surveys

```http
POST https://api.devrev.ai/surveys.submit
Content-Type: application/json
```

Submits a user response to a survey, which is defined by the survey ID.




## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.submit \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "object": "object",
  "survey": "survey"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.submit({
    object: "ACC-12345",
    survey: "survey"
});

```