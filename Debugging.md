# Debugging

## Retrieving logs for snap-in

Using DevRev CLI, you can retrieve build logs and runtime logs for your snap-ins.

### How to retrieve logs using DevRev CLI

<iframe width="100%" height="315" src="https://www.youtube.com/embed/5W70bbHxEJU?si=o2LQwy1GNC1U0n97" frameBorder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen />

* To retrieve logs for all snap-in packages/versions in your dev org after a particular timestamp, run the following command:

  ```bash
  devrev snap_in_package logs --after "2023-06-06T00:00:00Z" | jq
  ```

* To retrieve logs between two timestamps and use a cursor for pagination, run the following command:

  ```bash
  devrev snap_in_package logs --after "2023-06-06T10:24:17Z" --before "2023-06-07T00:00:00Z" --cursor cursor_from_previous_page | jq | code -
  ```

<Callout intent="note">
  By default, not specifying `--before` lists all logs until the current timestamp in descending order (latest logs at the top).
</Callout>

* To retrieve logs for a specific snap-in package, run the following command:

  ```bash
  devrev snap_in_package logs --after "2023-06-06T00:00:00Z" --filters '{"snap_in_package": {"values": ["don:integration:dvrv-us-1:devo/abcd:snap_in_package/abcdef"]}}' | jq | code -
  ```

* To retrieve logs containing the text "failed" but exclude logs with level "info", run the following command:

  ```bash
  devrev snap_in_package logs --after "2023-06-06T00:00:00Z" --query "failed" --filters '{"level": {"values": ["info"], "exclude": true}}' | jq | code -
  ```

The JSON response fields are filterable. For example, to view snap-in version execution logs only, add the filter on `process` field to match `function` and run the following command:

```bash
devrev snap_in_package logs --after "2023-06-06T00:00:00Z" --filters '{"snap_in_version": {"values": ["don:integration:dvrv-us-1:devo/abcd:snap_in_package/abcdef:snap_in_version/abcdef"]}, "process":{"values": ["function"]}}' | jq | code -
```

Similarly, you can filter only for build logs by filtering for `process = build`.

After creating the appropriate filters, to view the logs conveniently, run the following command:

<Callout intent="info">
  You can customize the part before `jq` according to your filters.
</Callout>

```bash
devrev snap_in_package logs --after "2023-06-06T00:00:00Z" --filters '{}' | jq -r '["total", .log_summary.total.value, "next_cursor", .next_cursor], (.logs[] | [.level,.timestamp,.msg]) | @tsv' | code -
```

## Troubleshooting

### Error "You are not authorized to perform this operation"

```bash
devrev snap_in draft
```

```txt
POST 'https://api.devrev.ai/internal/snap-ins.draft.create' failed with 403 Forbidden, {"debug_message":"Unauthorized You are not authorized to perform this operation. Ref: bc7b7f58-148c-479c-b0a6-b4cbe43dd8a6","message":"Forbidden","type":"forbidden"}
```

You are not an admin of the dev org where you want to create the snap-in.