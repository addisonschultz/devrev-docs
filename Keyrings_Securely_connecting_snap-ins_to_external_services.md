# Keyrings: Securely connecting snap-ins to external services

Keyrings provide a secure way to manage credentials for external services used within your DevRev snap-in. This eliminates the need to store sensitive information like passwords or access tokens directly in your code or configuration files, improving overall security.

Traditionally, developers might store these credentials directly in their snap-in's code. This poses a significant security risk. If someone gains access to your code, they could also steal these sensitive credentials.

Keyrings provide a secure alternative. By storing credentials separately from your code, you ensure they remain hidden and inaccessible even if the code is compromised. This strengthens the overall security of your snap-in.

Imagine you're building a DevRev snap-in that helps manage your marketing campaigns across different platforms. This snap-in might need to connect to various external services like Facebook Ads, Mailchimp, and a project management tool like Asana.

Here's where DevRev keyrings come in:

You can define keyrings within your snap-in manifest for each external service you need to connect to.
During installation, users will be prompted to provide their credentials for each keyring (think of it like securely logging in to each service through your snap-in). These credentials are then stored securely in the keyrings.
When your snap-in needs to interact with a specific service, it retrieves the necessary credentials from the corresponding keyring (see snap-in resources) instead of your code. This keeps your sensitive information safe and isolated.

Think of keyrings as secure vaults within your snap-in, acting as a middleman between your snap-in and the external services it connects to. This ensures both security and a smooth user experience during installation.

## Supported credential types

* **OAuth 2.0 :** Streamline connections with popular services like Slack and Jira using pre-defined OAuth keyrings.
* **Secrets:** Store various secret configurations, including personal access tokens (PATs) and multi-field tokens (JSON) for broader service integrations.

## Access levels

* **User level:** Securely store credentials specific to individual users, allowing them to connect their own accounts to external services through your snap-in.
* **Organization level:** Share credentials across your organization for access to a single, shared account for an external service.

## Syntax

A syntax for defining keyrings within your snap-in manifest:

```yaml
keyrings:
  organization:
    - name: <name of the keyring>
      display_name: <display name of the keyring>
      description: <description of the keyring>
      types:
        - <id of the keyring type>
  user:
    - name: <name of the keyring>
      display_name: <display name of the keyring>
      description: <description of the keyring>
      types:
        - <id of the keyring type>
```