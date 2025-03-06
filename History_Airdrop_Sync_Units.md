# History Airdrop Sync Units

```http
GET https://api.devrev.ai/airdrop.sync-units.history
```

Gets a list of sync unit historical records.



## Query Parameters

- Id (required): Sync unit that will be used for sync history listing.
- Cursor (optional): The cursor to resume iteration from. If not provided, then iteration
starts from the beginning.

- FilterHasErrorsOrWarnings (optional): Filter for sync runs that have errors.
- FilterMode (optional): Mode of the sync run.
- FilterStartedBy (optional): User who started the sync run.
- FilterState (optional): State of the sync run.
- Limit (optional): The maximum number of items to return. The default is '50'.

- Mode (required): The iteration mode to use, otherwise if not set, then "after" is
used.


## Response Body

- 200: List sync history response.

## Examples

```shell
curl -G https://api.devrev.ai/airdrop.sync-units.history \
     -H "Authorization: Bearer <token>" \
     -d id=id \
     -d mode=after
```