# Send Notifications

```http
POST https://api.devrev.ai/notifications.send
Content-Type: application/json
```

Generate a notification.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/notifications.send \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "notifications": [
    {
      "type": "generic_notification",
      "event_type": "alert",
      "metadata": [
        {
          "action": {
            "clickable_action": {}
          },
          "content_template": "content_template"
        },
        {
          "action": {
            "clickable_action": {}
          },
          "content_template": "content_template"
        }
      ]
    },
    {
      "type": "generic_notification",
      "event_type": "alert",
      "metadata": [
        {
          "action": {
            "clickable_action": {}
          },
          "content_template": "content_template"
        },
        {
          "action": {
            "clickable_action": {}
          },
          "content_template": "content_template"
        }
      ]
    }
  ]
}'
```

```typescript
import { DevRevClient, DevRev } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.notifications.send({
    notifications: [{
            type: "generic_notification",
            eventType: DevRev.GenericNotificationEventType.Alert,
            metadata: [{
                    contentTemplate: "content_template"
                }]
        }]
});

```