# Export Works

```http
GET https://api.devrev.ai/works.export
```

Exports a collection of work items.



## Query Parameters

- AppliesToPart (optional): Filters for work belonging to any of the provided parts.
- CreatedBy (optional): Filters for work created by any of these users.
- First (optional): The number of work items to return. The default is '50', the maximum
is '5000'.

- IssueAccounts (optional): Filters for issues with any of the provided accounts.
- IssuePriority (optional): Filters for issues with any of the provided priorities.
- IssuePriorityV2 (optional): Filters for issues with any of the provided priority enum ids.

- IssueRevOrgs (optional): Filters for issues with any of the provided Rev organizations.

- IssueSlaSummaryStage (optional): Filters for records with any of the provided SLA stages.
- IssueSprint (optional): Filters for issues with any of the sprint.
- OwnedBy (optional): Filters for work owned by any of these users.
- ReportedBy (optional): Filters for work reported by any of these users.
- StageName (optional): Filters for records in the provided stage(s) by name.
- StagedInfoIsStaged (optional): Filters for issues that are staged.
- State (optional): Filters for work with any of the provided states.
- SyncMetadataExternalReference (optional): Filters for issues with this specific external reference.
- SyncMetadataLastSyncInStatus (optional): Filters for works with selected sync statuses.
- SyncMetadataLastSyncInSyncUnit (optional): Filters for works modified with selected sync units.
- SyncMetadataLastSyncOutStatus (optional): Filters for works with selected sync statuses.
- SyncMetadataLastSyncOutSyncUnit (optional): Filters for works modified with selected sync units.
- SyncMetadataOriginSystem (optional): Filters for issues synced from this specific origin system.

- Tags (optional): Filters for work with any of the provided tags.
- TicketChannels (optional): Filters for tickets with any of the provided channels.
- TicketGroup (optional): Filters for tickets belonging to specific groups.
- TicketIsFrozen (optional): Filters for frozen tickets.
- TicketIsSpam (optional): Filters for tickets that are spam.
- TicketNeedsResponse (optional): Filters for tickets that need response.
- TicketRevOrg (optional): Filters for tickets that are associated with any of the provided Rev
organizations.

- TicketSeverity (optional): Filters for tickets with any of the provided severities.
- TicketSlaSummaryStage (optional): Filters for records with any of the provided SLA stages.
- TicketSourceChannel (optional): Filters for tickets with any of the provided source channels.

- Type (optional): Filters for work of the provided types.

## Response Body

- 200: Success.

## Examples

```shell
curl https://api.devrev.ai/works.export \
     -H "Authorization: Bearer <token>"
```