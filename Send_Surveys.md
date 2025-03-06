# Send Surveys

```http
POST https://api.devrev.ai/surveys.send
Content-Type: application/json
```

Sends a survey on the specified channels.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/surveys.send \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "email": {
    "body": "body",
    "recipients": [
      "recipients",
      "recipients"
    ],
    "sender": "sender",
    "subject": "subject"
  }
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.surveys.send({
    email: {
        body: "body",
        recipients: ["recipients"],
        sender: "sender",
        subject: "subject"
    }
});

```