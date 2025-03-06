# Get Airdrop Sync Unit

```http
GET https://api.devrev.ai/airdrop.sync-units.get
```

Gets a single sync unit's information.



## Query Parameters

- Id (required): Requested sync unit ID.

## Response Body

- 200: Response containing the requested sync unit.

## Examples

```shell
curl -G https://api.devrev.ai/airdrop.sync-units.get \
     -H "Authorization: Bearer <token>" \
     -d id=id
```