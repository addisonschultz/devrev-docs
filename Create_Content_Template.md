# Create Content Template

```http
POST https://api.devrev.ai/content-template.create
Content-Type: application/json
```

Create the content template.



## Response Body

- 201: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/content-template.create \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "notification_content_template",
  "defaults": [
    {
      "body": "body",
      "title": "title"
    },
    {
      "body": "body",
      "title": "title"
    }
  ]
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.notifications.contentTemplateCreate({
    type: "notification_content_template",
    defaults: [{
            body: "body",
            title: "title"
        }]
});

```