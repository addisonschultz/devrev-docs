# Function invocation

A function can be invoked synchronously or asynchronously.

You need to implement the run method in your function. The run method is called when the function is invoked. The run method signature is defined below:

```typescript
type Context = {
    // ID of the dev org for which the function is being invoked.
    dev_oid: string;
    // ID of the automation/command/snap-kit Action/Event Source for which the function is being invoked.
    source_id: string;
    // ID of the snap-in as part of which the function is being invoked.
    snap_in_id: string;
    // ID of the snap-in Version as part of which the function is being invoked.
    snap_in_version_id: string;
    // This secrets map would contain some secrets which platform would provide to the snap-in.
    // `service_account_token`: This is the token of the service account which belongs to this snap-in. This can be used to make API calls to DevRev. 
    // `actor_session_token`: For commands, and snap-kits, where the user is performing some action, this is the token of the user who is performing the action.
    secrets: Record<string, string>;
};

type ExecutionMetadata = {
    // A unique id for the function invocation. Can be used to filter logs for a particular invocation.
    request_id: string;
    // Function name as defined in the manifest being invoked.
    function_name: string;
    // Type of event that triggered the function invocation as defined in manifest.
    event_type: string;
    // DevRev endpoint to which the function can make API calls.
    // Example : "https://api.devrev.ai/"
    devrev_endpoint: string;
};

type InputData = {
    // Map of organization inputs and their corresponding values stored in snap-in.
    // The values are passed as string and typing need to be handled by the function
    global_values: Record<string, string>;
    // Map of event sources and their corresponding ids stored in snap-in.
    // These could be used to schedule events on a schedule based event source.
    event_sources: Record<string, string>;
    // Map of secrets stored in the snap-ins including developer keyrings. The key is the secret name defined in manifest and value is the secret value.
    keyrings: Record<string, string>;
};

// Event sent to our app.
type FunctionInput = {
    // Actual payload of the event.
    payload: Record<string, any>;
    // Context of the function invocation.
    context: Context;
    // Metadata of the function invocation.
    execution_metadata: ExecutionMetadata;
    input_data: InputData;
};

async function run(events: []FunctionInput): any;

```

As of now, it's safe to assume that only one event is passed to the function at a time. The function can be invoked multiple times for multiple events.

The value returned from the `run` method is passed back in synchronous execution modes, such as commands, snap kit actions, and event source synchronous execution. In asynchronous execution modes, such as automation execution, the return value is ignored.