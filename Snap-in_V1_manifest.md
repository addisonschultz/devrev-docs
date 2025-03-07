# Snap-in V1 manifest

<Callout intent="note">
  The following guide is for the version 1 of the manifest spec. For the latest version, refer to [Manifest](/snapin-development/references/manifest).
</Callout>

The snap-in manifest is what the developers write to define a snap-in. The manifest has the following sections:

## Version

The version of the manifest. The below documentation is for version 1 and should be specified in the manifest as:

```yaml
version: 1
```

## Connections

Connections are specified in the manifest with the following syntax:

```yaml
connections:
  - name: <connection name to use in the snap-in>
    description: <detail about what this connection is used for>
    display_name: <name shown to the end-user>
    types: <list specifying what all types of connections could be selected by the end user for this connection>

  - name: <connection name to use in the snap-in>
    description: <detail about what this connection is used for>
    display_name: <name shown to the end-user>
    types: <list specifying what all types of connections could be selected by the end user for this connection>
```

Example:

```yaml
connections:
  - name: github
    description: GitHub token to be used to get PR details
    types:
      - devrev-github-pat
      - devrev-github-oauth
```

Service that stores these secrets and has the business logic to refresh tokens, when applicable. Here is the list of currently supported connection types - [Connections](/snapin-development/references/keyrings)

## Developer connections

Developer connections are defined during the development by the snap-in developer. They are available across all installations and invisible to the installer.
Only snap-in secret string type is supported for developer connections.

```yaml
developer_connections:
  - name: <connection name to use in the snap-in>
    description: <detail about what this connection is used for>
    display_name: <name shown to the developer>

  - name: <connection name to use in the snap-in>
    description: <detail about what this connection is used for>
    display_name: <name shown to the developer>
```

Example:

```yaml
developer_connections:
  - name: mongodb
    description: Store usage statistics
    display_name: MongoDB PAT

  - name: discord
    description: Access additional discord's API
    display_name: Discord PAT
```

The developer connection can be selected while creating the snap\_in\_version. DevRev CLI detects the developer connections in the manifest and prompts for them:

```bash
devrev snap_in_version create-one --manifest manifest.yaml
Please provide mapping for the developer connections:
Use the arrow keys to navigate: ↓ ↑ → ←
? mongodb:
  ▸ mongodb
    discord
```

<Callout intent="note">
  Developer connections can only be created in the UI. They are of type "snap-in Secret".
</Callout>

## Event sources

Event sources are specified in the manifest with the following syntax:

```yaml
    event-sources:
      - name: <event-source name to use in the snap-in>
        description: <detail about this event-source>
        display_name: <name shown to the end-user>
        type: <enum specifying what type of the source should be created>
        setup_instructions: <optional instructions shown to the end-user>
        config:
     <an object containing config specific to the event source>

      - name: <event-source name to use in the snap-in>
        description: <detail about this event-source>
        display_name: <name shown to the end-user>
        type: <enum specifying what type of the source should be created>
```

Here is the [list of supported event sources](/snapin-development/references/event-sources).

Example:

```yaml
event-sources:
  - name: devrev-webhook
    description: Events coming from GitHub
    display_name: DevRev webhook
    type: devrev-webhook
    config:
      event_types:
        - work_created
```

## Globals

Globals are implemented today using per-object schemas, which is a customization term to store custom schemas in line with the object. Each global's schema maps to a FieldDescriptor.

The definition of globals looks like this:

```yaml
globals:
  - name: <name of the global>
    description: <its description - what is it supposed to do>
    devrev_field_type: <type of the global>
    devrev_id_type: <if the field type is id, then what are the supported object types whose id this global can store>
    is_required: <is this a required input?>
    default_value: <the default value for this global>
    ui:
      display_name: <display name for the input field>
```

## Tags

Define a tag by passing just the name and description of the tag.

Example:

```yaml
tags:
  - name: github.branch.name
    description: Tag storing github branch name.
```

## Commands

In the manifest, you need to specify the name of the command, its namespace, the surfaces where it can show up (such as comment discussions), a description that can show up on the UI, usage hints, and the function to be triggered when the command is invoked.

```yaml
commands:
  - name: summarize
    namespace: turing
    description: Summarizes the conversation
    surfaces:
      - surface: discussions
        object_types:
          - conversation
    usage_hint: "number of tokens to generate"
    function: generate_summary
```

For commands, the `<name, namespace>` pair should be unique across the Org in which it's installed.

## Functions

In the manifest, all you need to tell is the name of the function, and its description, just like tags:

```yaml
functions:
  - name: create_work
    description: Function containing logic to create a DevRev work.

  - name: post_message
    description: Function containing logic to post a message on newly created work.
```

For functions, you also need to provide the actual JS/TS code behind this function, for that, you can refer to the README in the provided template.

## Automations

Automation is where you would link events from the event sources to your function. The definition of automations looks like this:

```yaml
automations:
  - name: <name of the automation>
    source: <name of the event source specified in the manifest from which the events coming in could trigger this automation>
    event_types:
      - <event from the source on which you need to run the code>
    function: <name of the function specified in the manifest which should be run>
```

For custom event sources, whatever event key you emit from your policy, the event name would be "custom:`<your event key>`".