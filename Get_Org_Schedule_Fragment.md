# Get Org Schedule Fragment

```http
GET https://api.devrev.ai/org-schedule-fragments.get
```

Gets an organization schedule fragment.



## Query Parameters

- Id (required): Organization schedule Fragment ID.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/org-schedule-fragments.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```