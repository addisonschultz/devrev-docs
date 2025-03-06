# Personal-Data Rev Users

```http
POST https://api.devrev.ai/rev-users.personal-data
Content-Type: application/json
```

Retrieves data of a contact.



## Response Body

- 200: Response for the contacts personal data export request. Response is
empty as the process is asynchronous. Upon completion, the user will be
notified.


## Examples

```shell
curl -X POST https://api.devrev.ai/rev-users.personal-data \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "email": "email"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.compliance.getRevUsersPersonalData({
    email: "email"
});

```