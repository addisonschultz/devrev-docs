# Resources Snap Ins

```http
GET https://api.devrev.ai/snap-ins.resources
```

Gets snap-in resources for a user in a snap-in.



## Query Parameters

- Id (required): The ID of the snap-in to get resources for.
- User (required): The ID of the user to get resources for.

## Response Body

- 200: Success.

## Examples

```shell
curl -G https://api.devrev.ai/snap-ins.resources \
     -H "Authorization: Bearer <token>" \
     -d id=id \
     -d user=user
```