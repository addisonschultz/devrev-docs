# Snap-in triggered by a DevRev event

## Introduction

In this tutorial, you'll learn to create a dynamic snap-in that responds to both DevRev Webhook events triggered by the creation of a [work](https://docs.devrev.ai/product/core) and specialized [command](/snapin-development/references/commands) within DevRev.

The focus is on the process of working with the payload associated with these events. The objective is to adeptly extract pertinent fields from the payload within the defined functions, subsequently executing a well-defined action. This action involves the addition of a comment to the object timeline, a feature that can be conveniently customized.

## Background context

1. **Webhook event handling**: Understand the intricacies of responding to a
   DevRev webhook event, specifically focused on work creation.

2. **Command-based activation**: Explore how the snap-in can be triggered by a
   dedicated command within the DevRev environment.

3. **Payload exploration**: Delve into the payload structure, gaining insights
   into how to efficiently extract essential fields from within the functions.

4. **Action execution**: Become proficient in executing a specified action - adding
   a customizable comment to the object timeline.

To learn more, refer to the [Using a snap-in to perform a DevRev action](/snapin-development/tutorials/timer-ticket-creator) tutorial.

<Steps>
  ### Installation guide

  * Install [DevRev CLI](/snapin-development/references/cli-install)
  * Install [jq](https://stedolan.github.io/jq)
  * Install [DevRev SDK](https://www.npmjs.com/package/@devrev/typescript-sdk?activeTab=readme)

  <Callout intent="info">
    If you did not follow the [getting started](/snapin-development/tutorials/getting-started) tutorial then follow these steps to authenticate and initialize the snap-in TypeScript template:

    ```bash
    devrev profiles authenticate -o <dev-org-slug> -u <youremail@yourdomain.com>
    ```

    ```bash
    devrev snap_in_version init
    ```
  </Callout>

  #### Trigger

  To invoke the snap-in, two distinct triggers are implemented:

  1. **Creation of work item**: This trigger is activated when new objects of type
     **Issue** or **Ticket** are created in DevRev.

  2. **Text command**: This manual trigger is achieved by utilizing a slash
     command in the **Discussions** tab of the objects that support this feature.

  #### Action

  To implement the desired action of adding a comment to the object timeline, it
  is essential to identify the appropriate \[API]
  for this task. In this scenario, the `/timeline-entries.create` API is the
  designated choice for executing the action of adding a text comment from the
  snap-in. To accomplish this task, the DevRev SDK is employed.

  ### Creating the snap-in

  #### Updating the manifest

  The next step involves updating the manifest to define key attributes of
  the snap-in. This includes deciding on the name and providing a descriptive
  overview that is visible to users, offering context about the snap-in's
  purpose.

  ```yml
  version: "2"

  name: Sample snap-in
  description: Snap-in to add comments for demonstration purpose.

  service_account:
    display_name: "DevRev Bot"
  ```

  ### Event source

  Following the manifest update, the next step is to incorporate the [event source](/snapin-development/references/event-sources).
  For this scenario, events from DevRev are essential. Therefore, an event source
  of type `devrev-webhook` is added. In the configuration, the event type is
  specified as `work_created`.

  ```yml
  event_sources:
    organization:
      - name: devrev-webhook
        display_name: DevRev
        type: devrev-webhook
        config:
          event_types:
            - work_created
  ```

  ### Input fields

  To enable users to configure specific comments, input fields must be defined.
  For our use case, the following input fields are specified:

  1. **Input field**: This text field empowers users to input a custom message to
     be added as a comment. The default value is set to "Message from the input
     field."

  2. **Should extra comment be added?**: This boolean field determines whether an
     additional comment should be included. The default value is set to true.

  3. **List of extra names**: This array field allows users to provide a list of
     names to be added as comments. The default value is set to \["name1",
     "name2"].

  By incorporating these input fields, the snap-in becomes more adaptable and
  user-friendly, enabling users to supply specific comments tailored to their
  needs.

  ```yml
  inputs:
    organization:
      - name: input_field_1
        description: Input field to add comment to the work item.
        field_type: text
        default_value: "Message from the input field."
        ui:
          display_name: Input Field 1

      - name: input_field_2
        description: Add extra comment.
        field_type: bool
        default_value: true
        ui:
          display_name: Should extra comment be added?

      - name: input_field_array
        description: List of names to add as comment.
        base_type: text
        field_type: array
        default_value: ["name1", "name2"]
        ui:
          display_name: List of extra names!
  ```

  ### Functions

  With the groundwork laid out, the next crucial step involves defining the
  functions responsible for handling the logic in TypeScript to add comments using
  the DevRev SDK. The actual implementation of these functions is added in
  the subsequent step.

  ```yml
  functions:
    - name: function_1
      description:
        Function to create a timeline entry comment on a DevRev work item created.
    - name: function_2
      description:
        Function to create a timeline entry comment on a DevRev work item on which
        comment is added.
  ```

  ### Automations

  With the building blocks in place, the final piece of the puzzle involves
  defining automations. These automations encapsulate a trigger and a
  corresponding function that executes when an event of a specified type occurs.

  ```yml
  automations:
    - name: convergence_automation_devrev
      source: devrev-webhook
      event_types:
        - work_created
      function: function_1
  ```

  ### Commands

  To accommodate the additional trigger, a [command](/snapin-development/references/commands) must be defined within the
  manifest file:

  ```yml
  commands:
    - name: comment_here
      namespace: devrev
      description: Command to trigger function to add comment to this work item.
      surfaces:
        - surface: discussions
          object_types:
            - issue
            - ticket
      usage_hint: "Command to add comment to this work item."
      function: function_2
  ```

  ### Function logic

  Having established the architectural framework for the snap-in, identified its
  triggers, and outlined the overall workflow, the next crucial phase involves
  crafting the functions - `function_1` and `function_2`. These functions serve as
  the engines driving the business logic behind the snap-in's behavior.

  ### Getting the payload

  To kickstart the implementation process, understanding the structure of the
  payload is paramount. Whether dealing with a work creation event or a command
  event, having insight into the payload's composition is crucial. In scenarios
  where the payload structure is known, implementation can proceed seamlessly.
  However, if the payload structure is uncertain or real data exploration is
  desired, logging the entire payload becomes an invaluable step.

  To achieve this, the following code snippet can be added to the `index.ts` file:

  ```ts
  export const run = async (events: any[]) => {
    console.info("events", JSON.stringify(events));
  };
  export default run;
  ```

  ### Handling DevRev event

  Having gained clarity on the expected payload structure, the next step involves
  crafting custom code to handle the incoming events. In this context, the
  objective is to print information based on the event type. The provided
  TypeScript snippet exemplifies a function, `handleEvent`, tailored for our use
  case.

  ```ts
  async function handleDevRevEvent(event: any) {
    // Extracting necessary credentials and configurations from the event context
    const devrevPAT = event.context.secrets.service_account_token;
    const API_BASE = event.execution_metadata.devrev_endpoint;

    // Setting up the DevRev SDK client
    const devrevSDK = client.setup({
      endpoint: API_BASE,
      token: devrevPAT,
    });

    // Extracting relevant information from the event payload
    const workCreated = event.payload.work_created.work;

    // Retrieving the comment input provided by the user
    const messageInput = event.input_data.global_values.input_field_1;

    // Building the initial comment body
    let bodyComment =
      "Hello World is printed on the work " +
      workCreated.display_id +
      " from the automation, with message: " +
      messageInput;

    // Checking if additional comments are requested
    const extraComment = event.input_data.global_values.input_field_2;
    const extraComments = event.input_data.global_values.input_field_array;

    // Appending extra comments to the body if requested
    if (extraComment) {
      for (let comment of extraComments) {
        bodyComment = bodyComment + " " + comment;
      }
    }

    // Creating the timeline entry comment using DevRev SDK
    const body = {
      object: workCreated.id,
      type: "timeline_comment",
      body: bodyComment,
    };
    const response = await devrevSDK.timelineEntriesCreate(body as any);

    // Returning the response from the DevRev SDK
    return response;
  }
  ```

  This function illustrates the process of handling events, extracting necessary
  information from the payload, and utilizing the DevRev SDK to create a timeline
  entry comment. It serves as a foundational template that can be adapted based on
  specific use cases and requirements.

  ### Handling command event

  For scenarios where a command event is triggered, a dedicated function,
  `handleCommandEvent`, can be implemented to handle the event appropriately. The
  provided TypeScript snippet outlines the structure of this function,
  demonstrating how to extract relevant information from the event payload and
  utilize the DevRev SDK to create a timeline entry comment.

  ```ts
  async function handleCommandEvent(event: any) {
    // Extracting necessary credentials and configurations from the event context
    const devrevPAT = event.context.secrets.service_account_token;
    const API_BASE = event.execution_metadata.devrev_endpoint;

    // Setting up the DevRev SDK client
    const devrevSDK = client.setup({
      endpoint: API_BASE,
      token: devrevPAT,
    });

    // Extracting relevant information from the event payload
    const workCreated = event.payload.source_id;

    // Building the comment body for command events
    const bodyComment = "Hello World is printed on the work from the command.";

    // Creating the timeline entry comment using DevRev SDK
    const body = {
      object: workCreated,
      type: "timeline_comment",
      body: bodyComment,
    };

    // Sending the request to create the timeline entry comment
    const response = await devrevSDK.timelineEntriesCreate(body as any);

    // Returning the response from the DevRev SDK
    return response;
  }
  ```

  ### Deploying the snap-in to your organization

  Upon completing and validating the code changes, the next crucial step is
  deploying the snap-in to your organization. Follow these steps for a seamless
  deployment:

  1. Navigate to the `code` folder in your project directory.

  2. Execute the following commands in sequence to build, package, and create the
     necessary artifacts:

     ```bash
     npm install
     npm run build
     npm run package
     ```
</Steps>

## Resources

The final snap-in code and manifest can be found
[here](https://github.com/devrev/snap-in-examples/tree/main/4-sample-snap-in)