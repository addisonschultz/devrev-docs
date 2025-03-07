# Developer keyrings

In addition to keyrings for storing user or organization credentials, DevRev also offers a special type called developer keyrings. These keyrings cater specifically to developers during the snap-in creation process.

Unlike other keyrings that store user credentials, developer keyrings are designed to hold sensitive information needed by the developer during development and execution of any particular task. These secrets are provided by you, the developer, during the creation of a snap-in version. They are not exposed to users and are stored separately from the snap-in itself.

## Snap-in secrets

A snap-in secret is a simple way to store any plain text secret your snap\_in requires. It's ideal for sensitive information that doesn't require complex formatting.

To create a snap-in secret in the UI, go to the snap-in page **Connection** tab and find the `snap_in_secret` keyring type.

To create a snap-in secret with the CLI, run the following command:

```bash
echo \"<SECRET>\" | devrev developer_keyring create snap-in-secret <KEYRING NAME>
```

## OAuth secrets

The OAuth secret is specifically designed to store OAuth client credentials securely. It requires two fields:

* `client_id`: The client ID provided by the OAuth provider.
* `client_secret`: The client secret provided by the OAuth provider.

To create an OAuth secret with the CLI, run the following command:

```bash
echo '{"client_id":"<CLIENT ID>","client_secret":"<CLIENT SECRET>"}' | devrev developer_keyring create oauth-secret <KEYRING NAME>
```

## Developer keyrings in the snap-in manifest

Once you've created the keyring, you can use it in your snap-in by referencing the keyring name in the snap-in manifest file.

Syntax:

```yaml
  developer_keyrings:
    - name: <name of the keyring>
      description: <description of the keyring>
      display_name: <display name of the keyring>
```

When creating a new `snap_in_version` using the developer tools, you will be prompted to provide the values for the declared developer keyrings. This ensures that the sensitive information is securely stored and accessible to your snap-in at runtime.