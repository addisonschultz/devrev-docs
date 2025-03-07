# Secret configurations: Securely storing credentials

Secret configurations are a type of keyring well-suited for storing credentials like personal access tokens (PATs) and multi-field tokens (often stored in JSON format).

## PAT keyrings

*Personal access tokens (PATs)* are API keys generated by services like GitHub or GitLab, or by cloud platforms like AWS or Azure. These tokens grant programmatic access to specific resources or functionalities within the service, on behalf of a user.

Imagine your snap-in needs to interact with a user's GitHub repository. Instead of embedding the user's username and password directly in your code (a major security risk!), you can leverage secret configurations. During installation, your snap-in can prompt the user to provide their PAT for GitHub access. This PAT is then securely stored within a secret configuration keyring. Whenever your snap-in needs to interact with the user's GitHub repository, it retrieves the PAT from the keyring and uses it for authorization.

To use secret configurations in your snap-in, you need to declare them in your snap-in's manifest file. Here's a syntax of how you can declare a secret configuration keyring:

```yaml
keyrings:
  organization:
    - name: <name of the keyring>
      display_name: <display name of the keyring>
      description: <description of the keyring>
      types:
        - snap-in-secret
  user:
    - name: <name of the keyring>
      display_name: <display name of the keyring>
      description: <description of the keyring>
      types:
        - snap-in-secret
```

DevRev offers pre-defined keyring types for simplified credential management. This pre-defined type eliminates the need to create a custom keyring type specifically for PATs.

## Multi-field keyrings

*Multi-field tokens* are a broader category that often come in JSON format. They can contain various fields with different pieces of information needed for authorization with a service.

Some services might use custom authentication mechanisms that require more than just a single token value. These services might provide credentials in JSON format, containing fields like access keys, secret keys, or expiration times. Secret configurations offer a secure way to store these multi-field tokens within your snap-in.

To use secret configurations in your snap-in, you need to declare them in your snap-in's manifest file. Here's a syntax of how you can declare a secret configuration keyring:

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

This section defines a keyring within your organization. You can specify the keyring's name, a user-friendly display name for during installation, and a description explaining its purpose. Finally, you associate this keyring with a specific keyring type ID defined later.

```yaml
keyring_types:
  - id: <id of the keyring type>
    name: <name of the keyring type>
    description: <description of the keyring type>
    kind: "secret" # The kind field specifies the type of keyring.
    secret_config: # The secret_config section is used to define the fields in the secret.
      fields: # optional: data that the user shall provide in the input form when creating the connection. Each element represents one input field. Fields will be included in the final JSON secret. If omitted, the user will be asked for a generic secret.
        - id: <field_id>
          name: <field_name>
          description: <field_description>
        - id: <field_id>
          name: <field_name>
          description: <field_description>
          is_optional: <true/false> # optional: whether the field is optional or not. Default is false.
      token_verification: # The token_verification section is used to verify the token provided by the user.
        url: <url> # The URL to which the token will be sent for verification.
        method: <method> # The HTTP method to be used for the verification request.
        headers:
            <header_name>: <header_value> # optional: headers to be included in the verification request.
        query_params:
            <param_name>: <param_value> # optional: query parameters to be included in the verification request.
```

## Basic authentication with keyrings

For more information about basic authentication, you can refer to the Wikipedia article: [Basic authentication](https://en.wikipedia.org/wiki/Basic_access_authentication). This resource provides detailed information about the protocol and its potential security considerations.

Here's an syntax of how you can define a secret configuration keyring for basic authentication in your snap-in's manifest file:

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

This section defines a keyring within your organization. You can specify the keyring's name, a user-friendly display name for during installation, and a description explaining its purpose. Finally, you associate this keyring with a specific keyring type ID defined later.

```yaml
keyring_types:
  - id: <id of the keyring type>
    name: <name of the keyring type>
    description: <description of the keyring type>
    kind: "secret" # The kind field specifies the type of keyring.
    is_subdomain: <true/false> # optional: whether the keyring is a subdomain keyring or not. Default is false.
    secret_config: # The secret_config section is used to define the fields in the secret.
      secret_transform: <jq query> # example: .field_1 + ":" + .field_2 | @base64
      fields: # optional: data that the user shall provide in the input form when creating the connection. Each element represents one input field. Fields will be included in the final JSON secret. If omitted, the user will be asked for a generic secret.
        - id: <field_id_1>
          name: <field_name>
          description: <field_description>
        - id: <field_id_2>
          name: <field_name>
          description: <field_description>
      # The token_verification section is used to verify the token provided by the user.
      token_verification: # The token_verification section is used to verify the token provided by the user.
        url: <url> # The URL to which the token will be sent for verification.
        method: <method> # The HTTP method to be used for the verification request.
        headers:
            <header_name>: <header_value> # optional: headers to be included in the verification request.
        query_params:
            <param_name>: <param_value> # optional: query parameters to be included in the verification request.
```

* The `secret_transform` field is intended for more advanced scenarios where the secret needs to be transformed before use. For example, it could be used to hash a password before storing it within the keyring. The jq query provided in this field will be applied to the secret data before it is stored.
* The `is_subdomain` field is optional and specifies whether the keyring contains a subdomain. Enabling this field allows the keyring to get the subdomain from the user during creation. This is useful when the keyring requires a subdomain as part of the configuration.

### Keyring types

The supported keywords that can be dynamically inserted into URLs, headers, and query parameters within your custom keyring type configuration.

* `[API_KEY]`: The API key obtained from the secret configuration.
* `[SUBDOMAIN]`: The subdomain obtained from the secret configuration.
* `[FIELD_ID]`: The field ID obtained from the secret configuration.

Here, you can refer to the [keyring type examples](https://github.com/devrev/snap-in-examples/tree/main/13-keyring-type).