# Prepare Artifacts Versions

```http
POST https://api.devrev.ai/artifacts.versions.prepare
Content-Type: application/json
```

Prepares a new version for an artifact, returning the URL and form data
to upload the updated file.




## Response Body

- 200: The response to preparing a new artifact version.

## Examples

```shell
curl -X POST https://api.devrev.ai/artifacts.versions.prepare \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "id": "id"
}'
```

```typescript
import { DevRevClient } from "@devrev/api";

const client = new DevRevClient({ token: "YOUR_TOKEN" });
await client.artifacts.versionsPrepare({
    id: "ARTIFACT-12345"
});

```