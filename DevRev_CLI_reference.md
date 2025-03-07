# DevRev CLI reference

The following is a list of DevRev CLI commands:

## CLI version

Check the version of CLI:

```bash
devrev --version
```

## CLI help

To check all the available commands, run the following command:

```bash
devrev --help
```

Use `devrev [command] --help` for more information about a command.

## Authentication

<AccordionGroup>
  <Accordion title="Authenticate">
    To authenticate, run the following command:

    ```bash
    devrev profiles authenticate --org <DevOrg-slug-name> --usr <your-email@example.com>
    ```

    **Arguments**:

    * `<DevOrg-slug-name>`: The unique slug name of your DevOrg to which you want to log in.

    * `<your-email@example.com>`: Your registered user email for profile.

    The browser opens up and asks you to log in to DevRev. Once you log in, a local dev org profile is created and an access token is stored.
  </Accordion>

  <Accordion title="Authenticate using dev token">
    To set up authentication using the DevRev token, run the following command:

    <Callout intent="info">
      Using DevRev's interface, you can generate a DevRev token.
    </Callout>

    ```bash
    echo $DevRevToken | devrev profiles set-token --org <dev-org-name> --usr <email>
    ```

    It enables CLI operations on the dev org.
  </Accordion>
</AccordionGroup>

## Snap-in package

<AccordionGroup>
  <Accordion title="Create a snap-in package">
    To create a snap-in package, run the following command:

    ```bash
    devrev snap_in_package create-one --slug <slug name>
    ```

    For example:

    ```bash
    devrev snap_in_package create-one --slug github | jq .
    ```

    When the snap-in package is created, its ID is stored in the [snap-in context](#snap-in-context). Run the following command to view the ID:

    ```bash
    devrev snap_in_package show [id]
    ```

    For example:

    ```bash
    devrev snap_in_package show | jq .
    ```

    `[id]` is optional. If not provided, it uses the snap-in package ID from the [snap-in context](#snap-in-context).
  </Accordion>

  <Accordion title="Delete a snap-in package">
    To delete a snap-in package, run the following command:

    ```bash
    devrev snap_in_package delete-one [id]
    ```

    For example:

    ```bash
    devrev snap_in_package delete-one | jq .
    ```

    If `id` isn't provided, it picks up the `snap-in package id` from the [snap-in context](#snap-in-context).
  </Accordion>

  <Accordion title="List the snap-in package">
    To list the snap-in package, run the following command:

    ```bash
    devrev snap_in_package list
    ```

    For example:

    ```bash
    devrev snap_in_package list | jq .
    ```
  </Accordion>

  <Accordion title="Logs for the snap-in package">
    To view the snap-in package logs, run the following command:

    ```bash
    devrev snap_in_package logs
    ```

    For example:

    ```bash
    devrev snap_in_package logs | jq .
    ```

    **Additional flags**:

    * `--after` string timestamp after which to fetch logs. For example, 2023-01-15T10:24:17Z. Defaults to 15 minutes earlier.
    * `--before` string timestamp before which to fetch logs. For example, 2023-02-15T10:24:17Z. Defaults to now.
    * `--filters` string Filters for the log message as a JSON. For example, `{"level": {"values": ["info"]}, "dev_org": {"exclude": true, "values": ["don:identity:<partition>:devo/<dev-org-id>"]} }`
    * `--limit` uint32 Number of logs to fetch.
  </Accordion>
</AccordionGroup>

## Snap-in version

<AccordionGroup>
  <Accordion title="Create a snap-in version">
    To create a snap-in version, run the following command:

    ```bash
    devrev snap_in_version create-one --path <path to the snap-in code>
    ```

    For example:

    ```bash
    devrev snap_in_version create-one --path ./code
    ```

    Once the snap\_in\_version is created, its ID is stored in the snap-in context too.

    **Additional flags**:

    * `--package <id>` : Optional. If not provided, it uses the id from the [snap-in context](#snap-in-context).
    * `--manifest <path>`: specify the path to the manifest.yaml file using this flag.
    * `--archive <path>` : specify the path to the archive file (build.tar.gz) using this flag.
    * `--create-package`: creates a new snap\_in\_package in interactive mode and then creates a snap-in version using the newly created snap-in package id.
  </Accordion>

  <Accordion title="Show the snap-in version">
    To show the snap-in version, run the following command:

    ```bash
    devrev snap_in_version show [id]
    ```

    For example:

    ```bash
    devrev snap_in_version show | jq .
    ```

    `[id]` is optional. If not provided, it uses the snap\_in\_version id stored in the [snap-in context](#snap-in-context).
  </Accordion>

  <Accordion title="Delete the snap-in version">
    To delete a snap-in version, run the following command:

    ```bash
    devrev snap_in_version delete-one [id]
    ```

    For example:

    ```bash
    devrev snap_in_version delete-one | jq .
    ```

    `[id]` is optional. If not provided, it uses the id stored in the [snap-in context](#snap-in-context).
  </Accordion>

  <Accordion title="List the snap-in versions">
    To list the snap-in version, run the following command:

    ```bash
    devrev snap_in_version list
    ```

    For example:

    ```bash
    devrev snap_in_version list | jq .
    ```

    **Additional flags**:

    * `--package <id>`: Optional. If not provided, it uses the id from the [snap-in context](#snap-in-context).
  </Accordion>
</AccordionGroup>

## Snap-in

<AccordionGroup>
  <Accordion title="Create a snap-in draft">
    To create a snap-in draft instance, run the following command:

    ```bash
    devrev snap_in draft --snap_in_version [id]
    ```

    For example:

    ```bash
    devrev snap_in draft | jq .
    ```

    **Additional flags**:

    * `--snap_in_version [id]`: Optional. If not provided, it uses the snap-in version ID from the [snap-in context](#snap-in-context).

    Once the snap\_in draft command is successful, it also generates the interface link.
  </Accordion>

  <Accordion title="Update the snap-in with keyrings and inputs">
    To update the snap-in with keyrings and inputs, run the following command:

    ```bash
    devrev snap_in update [id]
    ```

    For example:

    ```bash
    devrev snap_in update
    ```

    `[id]` is optional. If not provided, it uses the snap\_in id stored in the [snap-in context](#snap-in-context).

    For non-interactive mode, use the following command with the appropriate values:

    ```bash
    echo '{"connection":[{"name":"github-oauth", "reference":"test 1"},{"name":"github", "reference":"test 2"}], "global":[{"name":"post_message","value":"some-value"},{"name":"put_message","value":"some-value"}]}' | devrev snap_in update
    ```
  </Accordion>

  <Accordion title="Activate the snap-in">
    To activate a snap-in, run the following command:

    ```bash
    devrev snap_in activate [id]
    ```

    `[id]` is optional. If not provided, it uses the ID stored in the local profile.
  </Accordion>

  <Accordion title="Deactivate the snap-in">
    To deactivate a snap-in, run the following command:

    ```bash
    devrev snap_in deactivate [id] [--force]
    ```

    `[id]` is optional. If not provided, it uses the ID stored in the local profile.

    `--force` flag deactivates the snap-in even if the `deactivate` hook fails. If the flag isn't specified, then the snap-in moves to the *Error* state if the `deactivate` hook fails.
  </Accordion>

  <Accordion title="Show the snap-in details">
    To show the snap-in details, run the following command:

    ```bash
    devrev snap_in show [id]
    ```

    `[id]` is optional. If not provided, it uses the ID stored in the local profile.
  </Accordion>

  <Accordion title="List the snap-ins">
    To list the snap-ins, run the following command:

    ```bash
    devrev snap_in list
    ```

    For example:

    ```bash
    devrev snap_in list | jq .
    ```
  </Accordion>

  <Accordion title="Delete a snap-in">
    To delete a snap-in, run the following command:

    ```bash
    devrev snap_in delete-one [id] [--force]
    ```

    `[id]` is optional. If not provided, it uses the id stored in the [snap-in context](#snap-in-context).

    The `--force` flag deletes the snap-in even if the `deactivate` hook fails. If the flag isn't specified, then the snap-in moves to the *Error* state if the `deactivate` hook fails.
  </Accordion>
</AccordionGroup>

## Snap-in context

The CLI persists in the context of the CLI in a snap-in context. The context is used to store the following information per snap-in package slug:

1. The ID of the snap-in package owning the slug.
2. The ID of the last created/upgraded snap-in version, if any.
3. The ID of the latest deployed snap-in, if any.

<AccordionGroup>
  <Accordion title="Show the snap-in context">
    To show the current snap-in context, run the following command:

    ```bash
    devrev snap_in_context show
    ```

    For example:

    ```bash
    devrev snap_in_context show
    ```

    Output:

    ```bash
    $ devrev snap_in_context show
    snap_in_context: <snap-in-context name>
    	snap_in: don:integration:<partition>:devo/<dev-oid>:snap_in/<snap-in-id>
    	snap_in_package: don:integration:<partition>:devo/<dev-oid>:snap_in_package/<snap-in-package-id>
    	snap_in_version: don:integration:<partition>:devo/<dev-oid>:snap_in_package/<snap-in-package-id>:snap_in_version/<snap-in-version-id>
    ```
  </Accordion>

  <Accordion title="List the snap-in context">
    To list the snap-in context, run the following command:

    ```bash
    devrev snap_in_context list
    ```

    For example:

    ```bash
    devrev snap_in_context list
    ```
  </Accordion>

  <Accordion title="Checkout a snap-in context">
    To check a different snap-in context, run the following command:

    ```bash
    devrev snap_in_context checkout <snap_in_context_name>
    ```

    For example:

    ```bash
    devrev snap_in_context checkout test_1
    ```
  </Accordion>
</AccordionGroup>