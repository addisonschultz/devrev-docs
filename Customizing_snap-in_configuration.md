# Customizing snap-in configuration

The DevRev snap-ins platform allows developers to define custom configuration pages for their snap-ins.

While the default configuration page automatically renders input fields for keyrings and inputs, there may be cases where a custom configuration page is more suitable:

* Improved user experience: Developers can design the configuration page to provide a more intuitive and streamlined experience for users setting up the snap-in.
* Advanced input handling: Custom configuration pages enable developers to handle complex input scenarios, such as fetching data from external systems to populate dropdown options or validating user input.
* Branding and styling: Developers can align the configuration page with their snap-in's branding and style guidelines, ensuring a consistent look and feel.

## Defining custom configuration pages

To create a custom configuration page for a snap-in, developers need to define the following in the snap-in manifest:

```yaml
snap_kit_actions:
  - name: org_snap_kit_action
    function: snap_in_configuration_handler
  - name: user_snap_kit_action
    function: snap_in_configuration_handler

functions:
  - name: snap_in_configuration_handler
    description: Handler for processing organization and user configuration options.
  - name: config_initializer
    description: Generates the initial configuration options for both organization and user.

configuration_handler:
  organization:
    initializer: config_initializer
    snap_kit_action_name: org_snap_kit_action
  user:
    initializer: config_initializer
    snap_kit_action_name: user_snap_kit_action
```

The `configuration_handler` section in the manifest connects the functions responsible for generating and processing the custom configuration page.

* `config_initializer`: Generates the initial configuration options for both organization and user. It is called when the configuration page is first loaded.
* `snap_in_configuration_handler`: This function processes the user and organization configuration options. It is triggered when actions are performed on the organization or user configuration snap-kit.

## Configuration functions

The configuration functions should return a valid snap-kit JSON that defines the layout and elements of the custom configuration page. Here's an example of a snap-kit JSON:

```json
{
  "snap_kit_body": {
    "body": {
      "snaps": [
        {
          "elements": [
            {
              "action_id": "user_snap_kit_action",
              "action_type": "remote",
              "elements": [
                {
                  "element": {
                    "action_id": "select",
                    "action_type": "client",
                    "initial_selected_option": {
                      "text": {
                        "text": "Ticket",
                        "type": "plain_text"
                      },
                      "value": "ticket"
                    },
                    "options": [
                      {
                        "text": {
                          "text": "Ticket",
                          "type": "plain_text"
                        },
                        "value": "ticket"
                      },
                      {
                        "text": {
                          "text": "Conversation",
                          "type": "plain_text"
                        },
                        "value": "conversation"
                      }
                    ],
                    "type": "static_select"
                  },
                  "type": "input_layout"
                }
              ],
              "submit_action": {
                "action_id": "next",
                "style": "primary",
                "text": {
                  "text": "Next",
                  "type": "plain_text"
                },
                "type": "button",
                "value": "next"
              },
              "type": "form"
            }
          ],
          "type": "card"
        }
      ]
    }
  }
}
```

In this example, the snap-kit renders a dropdown select for choosing between `Ticket` and `Conversation`, along with a `Next` button. When the **Next** button is clicked, the `user_snap_in_configuration_handler` function is invoked to process the user's selection.
In the snap-kit action handler, the `event.payload.action.id` can be used to determine the form being submitted and call the `snap-ins.update` API to update the configuration.

## Update snap-in inputs (beta)

Updates the inputs of a snap-in based on the inputs defined in the snap-in configuration.

**Note: This endpoint is currently in beta and may be subject to change in the future. Reach out to us via PLuG to subscribe to changes to beta endpoints.**

### Request payload

The request payload should be a JSON object with the following properties:

* `id` (string, required): The ID of the snap-in to update.
* `inputs_values` (object, required): An object containing the input values to update. The properties of this object should match the input names defined in the snap-in configuration.

Example payload:

```json
{
  "id": "snap_in_id",
  "inputs_values": {
    "part_picker": "don:core:dvrv-us-1:devo/XXXX/product:XXXX",
    "enum_list_picker": ["value-1", "value-2"]
  }
}
```

In the example above, the `part_picker` and `enum_list_picker` are the input names defined in the snap-in configuration, and their corresponding values are provided in the `inputs_values` object.

### Response

#### Success response

* Status Code: 200 OK
* Content-Type: application/json

Response body:

```json
{
  "data": {},
  "message": "Snap-in updated successfully",
  "success": true
}
```

#### Error response

If an error occurs while updating the snap-in, the response has the following format:

* Status Code: 4xx or 5xx
* Content-Type: application/json

Response body:

```json
{
  "data": {},
  "success": false
}
```

## Example usage

Here's an example of how to update the input values:

```typescript
async updateSnapInInputs(snapInId: string, inputsValues: Record<string, any>): Promise<HTTPResponse> {
  const payload: SnapInsUpdateRequest = {
    id: snapInId,
    inputsValues,
  };
  return this.updateSnapInInputs(payload);
}

async updateSnapInInputs(payload: SnapInsUpdateRequest): Promise<HTTPResponse> {
  try {
    
    await devrevSDK.snapInsUpdate(payload);
    return { data: {}, message: 'Snap-in updated successfully', success: true };
  } catch (error: any) {
    if (error.response) {
      const err = `Failed to update the snap-in. Err: ${JSON.stringify(error.response.data)}, Status: ${error.response.status}`;
      return { ...defaultResponse, message: err };
    } else {
      return { ...defaultResponse, message: error.message };
    }
  }
}
```

In this example, the `updateSnapInInputs` function takes the `snapInId` and `inputsValues` as parameters. The `inputsValues` object should contain the input names and their corresponding values as defined in the snap-in configuration.

The function constructs the payload object with the `snapInId` and `inputsValues`, and then calls the `updateSnapInInputs` function to make the POST request to the `snap-ins.update` endpoint.

If the request is successful, it returns a success response with a status code of 200 and a message indicating that the snap-in was updated successfully.

If an error occurs, it catches the error and returns an error response with an appropriate status code and an error message containing the error details.

<Note>
  Note: This endpoint is currently in beta, and its functionality or parameters may change in future updates.
</Note>

For more details on the snap-kit JSON format and available elements, refer to the [DevRev Snap-kit documentation](/snapin-development/references/snapkit).