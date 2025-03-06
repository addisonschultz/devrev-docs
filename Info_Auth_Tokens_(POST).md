# Info Auth Tokens (POST)

```http
POST https://api.devrev.ai/auth-tokens.info
Content-Type: application/json
```

Returns the Dev organization, user and token attributes extracted from
the auth token.




## Response Body

- 200: The Dev organization, user and token attributes extracted from the auth
token.


## Examples

```shell
curl -X POST https://api.devrev.ai/auth-tokens.info \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.authTokens.infoPost({
    "key": "value"
});

```