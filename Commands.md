# Commands

Using commands, the end user can interact with the snap-in through any defined surface. Under the `commands` section of the snap-in manifest, commands are defined. For example, you can define a command called `close` that moves an issue and its children to the completed state as follows:

```yaml
commands:
  - name: close
    namespace: devrev
    description: Closes the issue and all of its children issues.
    surfaces:
      - surface: discussions
        object_types:
          - issue
    usage_hint: "[text]"
    function: close_issue
```

The description of the command's fields is as follows:

* `name`: This is the name of the command used by the user to trigger it.
* `namespace`: it's used to distinguish commands installed from different snap-ins with the same name. Ensure the namespace is appropriate for your snap-in.
* `description`: Displayed when a list of commands is displayed to the user.
* `usage_hint`: A hint showing how to pass parameters to a command.
* `function`: When the command is executed, this function is triggered by the snap-in.
* `surfaces`: The surface where the command is enabled. More details in below table:

| Surface     | Object types | Remarks                                                    |
| ----------- | ------------ | ---------------------------------------------------------- |
| discussions | issue        | Enable command on the **Discussions** tab of issues        |
|             | ticket       | Enable command on the **Discussions** tab of tickets       |
|             | conversation | Enable command on the **Discussions** tab of conversations |
|             | part         | Enable command on the **Discussions** tab of parts         |
|             | workspaces   | Enable command on the **Discussions** tab of workspaces    |
|             | rev\_user    | Enable command on the **Discussions** tab of rev\_users    |
|             | account      | Enable command on the **Discussions** tab of accounts      |
|             | snap-in      | Enable command on the **Discussions** tab of snap\_ins     |
|             | opportunity  | Enable command on the **Discussions** tab of opportunity   |