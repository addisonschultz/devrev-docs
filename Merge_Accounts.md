# Merge Accounts

```http
POST https://api.devrev.ai/accounts.merge
Content-Type: application/json
```

Merges two accounts.



## Response Body

- 200: The response to merging an account.

## Examples

```shell
curl -X POST https://api.devrev.ai/accounts.merge \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "primary_account": "primary_account",
  "secondary_account": "secondary_account"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.accounts.merge({
    primaryAccount: "ACC-12345",
    secondaryAccount: "ACC-12345"
});

```