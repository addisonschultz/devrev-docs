# Upgrade snap-ins

The platform supports upgrading snap-in versions and corresponding snap-ins that haven't been published to the marketplace.

Upgrades can be performed using the `upgrade` subcommand of `snap_in_version`.

For example:

```bash
devrev snap_in_version upgrade -h
```

```txt
Upgrades a snap-in version.

Usage:
  devrev snap_in_version upgrade [flags]

Flags:
      --archive string    Archive path
      --force             Force upgrade of snap-in version even if it isn't compatible for upgrade with existing version
  -h, --help              help for upgrade
      --manifest string   Manifest path
      --path string       Path to the directory containing the manifest file and source code for snap-in functions
      --version string    snap-in version ID
```

You can pass only the manifest if that's the only thing that has changed. If you have changed the source code of the snap-in functions, you can pass the path to the directory containing the manifest file and the source code. The path to the archive file containing the functions can also be passed if you have already created it.Only one path, either directory containing the manifest file or archive should be passed.

The actual snap-in version to be upgraded is specified using the `--version` flag.

## Upgrade behavior

The upgrade command checks if the updated version is compatible with the existing version. If it isn't compatible, the upgrade fails. If you want to force an upgrade, you can use the `--force` flag.

If the upgrade is compatible, the upgrade command does the following:

1. Create a new snap-in version with the new manifest and source code. If either of them isn't provided, the existing manifest or source code is used.
2. Upgrade the snap-in to use the updated version.
3. Delete the old snap-in version.

If the upgrade isn't compatible, the upgrade command does the following:

1. Fail if the `--force` flag isn't used.
2. Delete the existing snap-in if the `--force` flag is used.

## Version compatibility

The following table shows compatibility between snap-in versions:

| Component        | Compatibility check                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Keyrings         | For existing keyrings: <br /> - The description can be changed. <br /> - The display name can be changed. <br /> - New values for allowed types under that connection could be added, but existing allowed types can't be removed. <br /> <br /> Any existing connection can be removed <br /> A new connection can't be added.                                                                                                                                         |
| Event sources    | For existing event sources: <br /> - The description can be changed. <br /> - The display name can be changed. <br /> - Type can't be changed. <br /> - Connection can't be changed but can be removed. <br /> - Config can change whether or not changes reflect depending on the event source type. Test if you change the config. <br /> - Instructions can change. <br /> <br /> An existing event source can't be removed. <br /> A new event source can be added. |
| Tags             | For existing tags: <br /> - The description can be changed. <br /> <br /> A new tag can be added. <br /> Any existing tags can be removed.                                                                                                                                                                                                                                                                                                                              |
| Automations      | For existing automations: <br /> - The description can be changed. <br /> - The source can be changed. <br /> - Allowed event types can be changed. <br /> - The function to execute can be changed. <br /> <br /> Any existing automation can be removed. <br /> A new automation can be added.                                                                                                                                                                        |
| Hooks            | For existing hooks: <br /> - The function to execute can be changed. <br /> <br /> Any existing hooks can be removed. <br /> A new hook can be added.                                                                                                                                                                                                                                                                                                                   |
| Functions        | For existing functions: <br /> - The description can be changed. <br /> - Actual code can be changed. <br /> <br /> Any existing function can be removed. <br /> A new function can be added.                                                                                                                                                                                                                                                                           |
| Commands         | For existing commands: <br /> - All properties can be changed. <br /> <br /> Any existing command can be removed. <br /> A new command can be added.                                                                                                                                                                                                                                                                                                                    |
| Snap-kit actions | For existing snap-kit-actions: <br /> - The description can be changed. <br /> - The function can be changed. <br /> <br /> Any existing snap-kit-action can be removed. <br /> A new snap-kit-action can be added.                                                                                                                                                                                                                                                     |
| Service account  | The display name of the service account can be changed.                                                                                                                                                                                                                                                                                                                                                                                                                 |
| Inputs           | Inputs can't be changed.                                                                                                                                                                                                                                                                                                                                                                                                                                                |

## Example scenarios

The following are some examples of when you might need to run these upgrades:

* Changing the source code of a function used in the snap-in
* Adding a new automation
* Adding a new command
* Changing the description of a snap-in
* Changing the identity of a snap-in (changing the service account)

## Idempotency

If you run the upgrade command for the same snap-in version multiple times, the command does the following:

1. Returns an already existing error if an upgrade is currently in progress or completed for the same snap-in version.
2. When the previous upgrade failed, starts another upgrade if the manifest is different or if the `--archive` or `--path` parameter is passed to the upgrade command.

## Checking status of the upgrade

When you run `devrev snap_in_version list` for the same package after the upgrade succeeds, you should see the updated snap-in version. In the list, you might see the old snap-in version and the updated snap-in version while the upgrade is in progress. In the case of a failure, you only see the old snap-in version.