# OAuth 2.0 configuration: Securely storing access tokens

OAuth 2.0 (Open Authorization) is a widely adopted standard for authorization that allows users to grant access to their accounts on one service (like Google or GitHub) to another application (like your DevRev snap-in) without needing to share their passwords directly. This approach enhances security and user convenience.

For comprehensive information about the OAuth specification, refer to the official documentation: [OAuth 2.0](https://oauth.net/2/).

## Using OAuth 2.0 keyrings

1. **Define the keyring:** Within your snap-in manifest, define a keyring specifically for OAuth credentials. DevRev offers pre-defined keyring types for popular services like Slack or Jira, simplifying the process.

2. **Provide credentials:** During development, you'll provide your developer keyring of type `oauth-secret` which contains client ID and client secret for the chosen service within the keyring definition. These credentials are securely stored and not distributed with your published snap-in.

3. **OAuth 2.0 flow:** When your snap-in needs to access user data from the external service, it initiates the OAuth flow. This typically involves redirecting the user to the service's login page and then back to your snap-in after successful authorization.

4. **Access tokens:** Upon successful authorization, the service provides your snap-in with an access token. This token is used to access user data on the service's behalf without requiring the user's password again.

5. **Refreshing tokens:** A key benefit of using keyrings for OAuth is that they can handle refreshing access tokens automatically. Most OAuth implementations issue a refresh token alongside the access token. This refresh token can be used to obtain a new access token before the current one expires. If the token is not provided or is expired, the user will need to re-authorize the connection.

6. **Revoking tokens:** For enhanced security, you can also configure your keyring to revoke access tokens when they are no longer needed. This ensures that even if a token is compromised, it can't be used to access user data.

7. **Organization data:** Optionally, you can configure your keyring to fetch additional information about the user's organization within the service. This can be useful for snap-ins that need to access organization-wide data.

### Keywords

The supported keywords that can be dynamically inserted into URLs, headers, and query parameters within your custom keyring type configuration.

* `[ACCESS_TOKEN]`: The access token obtained during the OAuth flow.
* `[REFRESH_TOKEN]`: The refresh token obtained during the OAuth flow.
* `[CLIENT_ID]`: The client ID obtained from the OAuth client credentials.
* `[CLIENT_SECRET]`: The client secret obtained from the OAuth client credentials.
* `[SCOPE]`: The scope of the OAuth flow.
* `[API_KEY]`: The API key obtained from the basic flow.

### Syntax

```yaml
developer_keyrings:
  - name: <keyring_name>
    description: <keyring_description>
    display_name: <keyring_display_name>

keyrings:
  organization:
    - name: <keyring_name>
      display_name: <keyring_display_name>
      description: <keyring_description>
      types:
        - <id of keyring_type>

keyring_types:
  - id: <keyring_type_id>
    name: <keyring_type_name>
    description: <keyring_type_description>
    kind: "oauth2"
    is_subdomain: <true/false> # optional: whether the keyring is a subdomain keyring or not. Default is false. It is used to get the subdomain from the user during creation.
    scopes: # Scopes that the connection can request, add more scopes if needed for your use case. Each scope should have a name, description and value.
      - name: <scope_name>
        description: <scope_description>
        value: <scope_value>
      - name: <scope_name>
        description: <scope_description>
        value: <scope_value>
    scope_delimiter: <scope_delimiter> # The delimiter used to separate scopes in the request.
    oauth_secret: <name of the developer keyring> # developer keyring that contains OAuth2 client ID and client secret. Shall be of type `oauth-secret`.
    # Authorizing Connection: The authorize section is used to get the authorization code from the user and exchange it for an access token.
    authorize: # The authorize section is used to get the authorization code from the user and exchange it for an access token.
      type: "config"
      auth_url: <auth_url> # The URL to which the user is redirected to authorize the connection.
      token_url: <token_url> # The URL to which the authorization code is sent to get the access token.
      grant_type: "authorization_code" 
      auth_query_parameters:
        <param_name>: <param_value>
        ....
      token_query_parameters:
        <param_name>: <param_value>
        ....
    # Fetching Organization Data: (Optional) This allows you to retrieve additional information about the user's organization within the service.
    organization_data: # Configuration for fetching organization data
      type: "config"
      url: <url> # The URL to which the request is sent to fetch organization data.
      method: <method> # The HTTP method used to send the request.
      headers:
        <header_name>: <header_value>
      query_parameters:
        <param_name>: <param_value>
      response_jq: <jq_filter> # The jq filter used to extract the organization data from the response.
    # Refreshing Access Token: (Optional) Defines how to automatically obtain a new access token when the current one expires.
    refresh: # The refresh section is used to refresh the access token using the refresh token.
      type: "config"
      url: <refresh_url> # The URL to which the refresh token is sent to get a new access token.
      method: <refresh_method> # The HTTP method used to send the refresh token.
      query_parameters:
        <param_name>: <param_value>
      headers:
        <header_name>: <header_value>
    # Revoking Access Token: (Optional) This allows you to revoke the access token after your snap-in no longer needs it, enhancing security.
    revoke: # The revoke section is used to revoke the access token.
      type: "config"
      url: <revoke_url> # The URL to which the access token is sent to revoke it.
      method: <revoke_method> # The HTTP method used to send the access token.
      headers:
        <header_name>: <header_value>
      query_parameters:
        <param_name>: <param_value>
```

Here, you can refer to the [keyring type examples](https://github.com/devrev/snap-in-examples/tree/main/13-keyring-type).