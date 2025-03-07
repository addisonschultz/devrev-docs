# Development best practices

## Act on specific webhook conditions

When writing an automation that listens to a webhook event, ensure you check for the specific conditions you want to act on. For example, if you are writing an automation that checks if the conversation state is moved to archived, you should check for the conversation\_updated webhook event and then check if the conversation\_state is archived. In this case, the automation only triggers when the conversation state changes to archived, not in any other state.

Debugging is easier when the conditions are specified and checked early in the code.

## Use the DevRev SDK

The DevRev SDK is a wrapper around the DevRev APIs, which makes them easier to use. It provides additional functionality such as retrying failed API calls. It's recommended to use the SDK instead of directly calling the APIs.

Check out our [DevRev SDK](https://www.npmjs.com/package/@devrev/typescript-sdk) for more information.

## Think from a snap-in installer perspective

Avoid developing snap-ins that depend on other snap-ins. Currently, the platform doesn't allow bundling of snap-ins. Requiring users to install multiple snap-ins that depend on each other results in installation complexities.

Most snap-in installers aren't developers, so consider the following tips when designing the configuration page:

* Avoid technical jargon for config names and descriptions.
* The descriptions should be adequate to guide the installer if there are no configurations. For example, some slash command snap-ins.
* Don't require users to understand technical formats such as JSON or XML.
* Prefer sensible defaults over obscure advanced options.
* In the config form, place the most important parameters at the top and use optional parameters when they aren't needed.
* Unless necessary for clarity, keep config names and descriptions concise.
* Name configs in a way that's familiar to you.

<Callout intent="tip" title="Coding tips">
  - If you are using async functions, remember to use await while calling them in your snap-in function code.
  - If the promise returned by the Run function is rejected, the snap-in will retry itself.
</Callout>