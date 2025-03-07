# Event sources

## Supported event source types and their event types

| Event source code   | Event source name   | Event type code                          | Remarks                                                                 | Documentation URL                                       |
| ------------------- | ------------------- | ---------------------------------------- | ----------------------------------------------------------------------- | ------------------------------------------------------- |
| devrev-webhook      | DevRev webhook      | All supported DevRev webhook event types | DevRev webhook events such as `work_created` and `conversation_updated` | [DevRev Webhook](#devrev-webhook)                       |
| flow-events         | Flow Events         | Configurable                             | Event sources schedule and publish events directly from a snap-in.      | [Scheduled events](#scheduled-events)                   |
| flow-custom-webhook | Flow Custom webhook | Configurable                             | A generic webhook with a URL and configurable authentication logic.     | [Generic event sources](#generic-event-sources)         |
| timer-events        | Timer Events        | `timer.tick`                             | Sends a `timer.tick` event based on a configured schedule.              | [Timer-based event sources](#timer-based-event-sources) |
| email-forward       | Email Forward       | `email.receive`                          | Used for receiving emails forwarded from an email inbox/mailing list.   | [Email-based event source](#Email-based-event-source)   |

## Event source instructions

You can provide custom instructions for each event source. These instructions are shown to the user when installing the snap-in. The instructions are written in markdown and can be provided in the `setup_instructions` field of the event source.

To provide dynamic instructions, you can access some metadata from event source objects. The following fields are accessible:

* `{{source.name}}`: Name of the event source
* `{{source.trigger_url}}`: Webhook URL
* `{{source.config.<field_name>}}`: Fields from within the event source configuration

For example:

```yaml
event_sources:
  organization:
    - name: argocd-source
      description: Events triggered by ArgoCD workflows
      display_name: ArgoCD
      type: flow-custom-webhook
      setup_instructions: |
        ## ArgoCD webhook
        Your webhook URL is `{{source.trigger_url}}`. You can use it to configure the ArgoCD webhook.
        For configuration instructions, refer to the [ArgoCD documentation](https://argo-cd.readthedocs.io/en/stable/operator-manual/notifications/services/webhook/).
      config:
        policy: |
          package rego
          output = {"event": event, "event_key": event_key} {
            event := input.request.body
            event_key := "argocd.workflow"
          } else = {"response": response } {
            response := {
            "status_code": 400
            }
          }
```

## DevRev Webhook

The `devrev-webhook` event source can be used to listen for events occuring on DevRev. These includes events like `work_created` and `conversation_updated`.
The payload of the events is defined by the Webhooks Event Schema.

### Webhook-event-request example:

```JSON
{
  "account_created": {
    "account": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "domains": [
        null
      ],
      "external_refs": [
        null
      ],
      "owned_by": [
        {}
      ],
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ],
      "tier": "string"
    }
  },
  "account_deleted": {
    "id": "ACC-12345"
  },
  "account_updated": {
    "account": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "domains": [
        null
      ],
      "external_refs": [
        null
      ],
      "owned_by": [
        {}
      ],
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ],
      "tier": "string"
    }
  },
  "conversation_created": {
    "conversation": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "description": "string",
      "group": {},
      "members": [
        {}
      ],
      "messages": [
        {}
      ],
      "metadata": {},
      "owned_by": [
        {}
      ],
      "stage": {},
      "tags": [
        {}
      ],
      "title": "string"
    }
  },
  "conversation_deleted": {
    "id": "string"
  },
  "conversation_updated": {
    "conversation": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "description": "string",
      "group": {},
      "members": [
        {}
      ],
      "messages": [
        {}
      ],
      "metadata": {},
      "owned_by": [
        {}
      ],
      "stage": {},
      "tags": [
        {}
      ],
      "title": "string"
    }
  },
  "dev_user_created": {
    "dev_user": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "display_picture": {},
      "email": "string",
      "full_name": "string",
      "phone_numbers": [
        null
      ],
      "state": "active",
      "external_identities": [
        {}
      ]
    }
  },
  "dev_user_deleted": {
    "id": "string"
  },
  "dev_user_updated": {
    "dev_user": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "display_picture": {},
      "email": "string",
      "full_name": "string",
      "phone_numbers": [
        null
      ],
      "state": "active",
      "external_identities": [
        {}
      ]
    }
  },
  "id": "string",
  "part_created": {
    "part": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "name": "string",
      "owned_by": [
        {}
      ],
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "part_deleted": {
    "id": "PROD-12345"
  },
  "part_updated": {
    "part": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "name": "string",
      "owned_by": [
        {}
      ],
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "rev_org_created": {
    "rev_org": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "account": {},
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "domain": "string",
      "external_ref": "string",
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "rev_org_deleted": {
    "id": "REV-AbCdEfGh"
  },
  "rev_org_updated": {
    "rev_org": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "account": {},
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "domain": "string",
      "external_ref": "string",
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "rev_user_created": {
    "rev_user": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "display_picture": {},
      "email": "string",
      "full_name": "string",
      "phone_numbers": [
        null
      ],
      "state": "active",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "external_ref": "string",
      "is_verified": true,
      "rev_org": {},
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "rev_user_deleted": {
    "id": "string"
  },
  "rev_user_updated": {
    "rev_user": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "display_name": "string",
      "display_picture": {},
      "email": "string",
      "full_name": "string",
      "phone_numbers": [
        null
      ],
      "state": "active",
      "artifacts": [
        null
      ],
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "description": "string",
      "external_ref": "string",
      "is_verified": true,
      "rev_org": {},
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ]
    }
  },
  "sla_tracker_created": {
    "sla_tracker": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z"
    }
  },
  "sla_tracker_deleted": {
    "id": "string"
  },
  "sla_tracker_updated": {
    "sla_tracker": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z"
    }
  },
  "tag_created": {
    "tag": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "allowed_values": [
        null
      ],
      "description": "string",
      "name": "string"
    }
  },
  "tag_deleted": {
    "id": "TAG-12345"
  },
  "tag_updated": {
    "tag": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "allowed_values": [
        null
      ],
      "description": "string",
      "name": "string"
    }
  },
  "timeline_entry_created": {
    "entry": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "labels": [
        null
      ],
      "object": "string",
      "object_display_id": "string",
      "object_type": "account",
      "reactions": [
        {}
      ],
      "thread": {},
      "visibility": "external",
      "artifacts": [
        null
      ],
      "body": "string",
      "body_type": "snap_kit",
      "snap_kit_body": {
        "body": {}
      },
      "snap_widget_body": [
        {}
      ]
    }
  },
  "timeline_entry_deleted": {
    "id": "don:core:<partition>:devo/<dev-org-id>:ticket/123:timeline_event/<timeline-event-id>"
  },
  "timeline_entry_updated": {
    "entry": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "labels": [
        null
      ],
      "object": "string",
      "object_display_id": "string",
      "object_type": "account",
      "reactions": [
        {}
      ],
      "thread": {},
      "visibility": "external",
      "artifacts": [
        null
      ],
      "body": "string",
      "body_type": "snap_kit",
      "snap_kit_body": {
        "body": {}
      },
      "snap_widget_body": [
        {}
      ]
    }
  },
  "timestamp": "2023-01-01T12:00:00.000Z",
  "type": "account_created",
  "verify": {
    "challenge": "string"
  },
  "webhook_created": {
    "webhook": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "event_types": [
        null
      ],
      "secret": "string",
      "status": "active",
      "url": "string"
    }
  },
  "webhook_deleted": {
    "id": "don:integration:<partition>:devo/<dev-org-id>:webhook/<webhook-id>"
  },
  "webhook_id": "don:integration:<partition>:devo/<dev-org-id>:webhook/<webhook-id>",
  "webhook_updated": {
    "webhook": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "event_types": [
        null
      ],
      "secret": "string",
      "status": "active",
      "url": "string"
    }
  },
  "work_created": {
    "work": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "applies_to_part": {},
      "artifacts": [
        null
      ],
      "body": "string",
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "owned_by": [
        {}
      ],
      "reported_by": [
        {}
      ],
      "stage": {},
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ],
      "target_close_date": "2023-01-01T12:00:00.000Z",
      "title": "string",
      "developed_with": [
        {}
      ],
      "priority": "p0"
    }
  },
  "work_deleted": {
    "id": "ISS-12345"
  },
  "work_updated": {
    "work": {
      "created_by": {},
      "created_date": "2023-01-01T12:00:00.000Z",
      "display_id": "string",
      "id": "string",
      "modified_by": {},
      "modified_date": "2023-01-01T12:00:00.000Z",
      "applies_to_part": {},
      "artifacts": [
        null
      ],
      "body": "string",
      "custom_fields": {},
      "custom_schema_fragments": [
        "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>"
      ],
      "owned_by": [
        {}
      ],
      "reported_by": [
        {}
      ],
      "stage": {},
      "stock_schema_fragment": "don:core:<partition>:devo/<dev-org-id>:custom_type_fragment/<custom-type-fragment-id>",
      "tags": [
        {}
      ],
      "target_close_date": "2023-01-01T12:00:00.000Z",
      "title": "string",
      "developed_with": [
        {}
      ],
      "priority": "p0"
    }
  }
}
```

### Webhook Filters

To limit the events being sent to a webhook, you can also specify a `jq` query as a filter. This filter is applied on the webhook before the event is dispatched. If no filter is specified, then all events are sent.

The `jq` query can reference the event payload as `.` and the user creating the webhook as `$user`. The `$user` object only contains one string field: the `id` of the webhook creator.

The filter must return a boolean value. If the filter returns `true`, the event is dispatched to the webhook. If the filter returns `false`, the event is not dispatched to the webhook.

For example, to create an event source which listens for issue creation and comments on issues, you can define the event source as follows:

```yaml
event_sources:
  organization:
    - name: devrev-webhook
      description: Events coming from DevRev for issues
      display_name: DevRev webhook
      type: devrev-webhook
      config:
        event_types:
          - work_created
          - timeline_entry_created
        filter:
          jq_query: |
            if .type == "work_created" then
              if (.work_created.work.type == "issue") then true
              else false
              end
            elif .type == "timeline_entry_created" then
              if (.timeline_entry_created.entry.type == "timeline_comment" and .timeline_entry_created.entry.object_type == "issue") then true
              else false
              end
            else false
            end
```

## Scheduled events

`flow-events` are an event source that snap-ins can use to publish or schedule events directly. This event source can then be used to trigger another automation. This capability makes it ideal for building snap-ins that need to act later. For example, sending reminders to issues still in the *Triage* stage.

You create an event source of type `flow-events`, and from your snap-in, you call the DevRev API to schedule an event for this event source. The following example illustrates how this works:

`manifest.yaml`

```yaml
version: "2"

service_account:
  display_name: Test bot

event_sources:
  organization:
    - name: devrev-webhook
      description: Event coming from DevRev
      display_name: DevRev
      type: devrev-webhook
      config:
        event_types:
          - work_created
    - name: scheduled-events
      description: Events scheduled from snap-ins
      display_name: scheduled-events
      type: flow-events

functions:
 - name: function_1
   description: Function 1
 - name: function_2
   description: Function 2

automations:
  - name: Schedule an event 30 seconds after work is created
    source: devrev-webhook
    event_types:
      - work_created
    function: function_1
  - name: Comment hello on scheduled work item
    source: scheduled-events
    event_types:
      - custom:work-created-scheduled-event
    function: function_2
```

In this example, the first automation schedules an event with a delay of 30 seconds for the event source `scheduled-events`.

The second automation then binds `function_2` to this event source. So the scheduled event executes `function_2` 30 seconds after the work is created.

In `function_1`, you can publish the event as follows:

```ts
  const url = "https://api.devrev.ai/event-sources.schedule";
  const work = event.payload.work_created.work;
  const delay_secs = 30;
  const event_payload = {
    "object_id": work.id,
    "name" : work.created_by.full_name,
    "delay": delay_secs,
  }
  const payload_bytes = Buffer.from(JSON.stringify(event_payload)).toString('base64');
  const publish_at = new Date(Date.now() + 1000 * delay_secs).toISOString();

  const req = {
    "id": event.input_data.event_sources["scheduled-events"],
    "payload": payload_bytes,
    "event_type": "work-created-scheduled-event",
    "publish_at": publish_at,
    "event_key": `delayed-run-${work.id}`
  }
  const response = await axios.post(url, req, {
    headers: {
      'Content-Type': 'application/json',
      authorization: event.context.secrets.service_account_token
    }
  });
  console.log('response: ', response.data);
```

In `function_2`, you can use the payload of the scheduled event as follows:

```ts
  const object_id = event.payload.object_id;
  const name = event.payload.name;
  const delay = event.payload.delay;
  console.log(`Received payload with object_id: ${object_id}, name: ${name}, delay: ${delay}`);
```

<Callout intent="note">
  The `/event-sources.schedule` API is currently in early access. For API details, see [event-sources-schedule-event](/beta/api-reference/event-source/event-sources-schedule-event).
</Callout>

To cancel scheduled events, you can utilize the `/event-sources.unschedule` API. For API details, see [event-sources-delete-scheduled-event](/beta/api-reference/event-source/event-sources-schedule-event).

## Generic event sources

You can create a generic event source if you need an event source not supported by DevRev. A generic event source includes a webhook URL and developer-provided code on how to validate the events coming on the URL.

For example, let's say you want to connect to a source that can publish events to a webhook URL, and it hashes the entire request payload with the shared secret and adds an HTTP header `X-Signature-256` with value as the hash. Then, you can provide the custom code (currently in [rego](https://www.openpolicyagent.org/docs/latest/policy-language/#what-is-rego)) to validate the payload with the same algorithm. You would also calculate the hash and verify with the value present in the header to avoid someone else tampering in between.

To create a generic event source in your manifest, you create an event source with the type `flow-custom-webhook` and `config` containing a key `policy` which contains the rego code.

The input passed to the policy is the following JSON:

```json
    {
      "parameters": "<a JSON which contains the parameters you have specified in your event source's `config.parameters` field>",
      "request": {
        "method": "<HTTP method of the request (GET, POST.)>",
        "query": "<key-value map of the query parameters in the request URL. The keys are case sensitive. This is of type map[string][]string.
           for example, if the query string is `a=1&b=2&b=3&c[]=4&c[]=5`, then the value of this field is `{"a": ["1"], "b": ["2", "3"], "c[]": ["4", "5"]}`>",
        "query_raw": "<The raw query string without the '?'.>",
        "headers": "<key-value (string) map of the request headers. Duplicate values for same `key` are overridden.
           Header keys are in Canonical-Header-Key format. For example, Content-Type, Accept-Encoding, and so on.>",
        "body": "<JSON body of the HTTP request received on the webhook. If Content-Type is application/x-www-form-urlencoded, then the body is parsed in the same way as the `query` field.",
        "body_raw": "<Raw body (bytes) of the HTTP request as a base64 string.>"
      }
    }
```

The policy must return an object `output` in the following format:

```json
    {
     "event": "[optional]
               A JSON representing the event to emit.
               This is `input.request.body` in most cases.
               If it is not present (or null), then the event is not published.",
     "event_key": "[required and non-empty if `event` is non-null]
                  `string` to represent the type of the event.
                  For example, file-created, pipeline-failed and so on.
                  This `event_key` is prefixed with 'custom:' and published to DevRev.
                  So, Snap-ins that want to use this event should use the `event_type` as `custom:event-key` in their automations.",
     "response": `[optional]
          A JSON containing following fields:
          {
              "status_code": "[optional]
                             `integer` HTTP status code to return to the caller.
                             Only valid HTTP codes allowed.
                             Defaults to 200.",
              "body": "[optional]
                       `string` or `JSON` for HTTP body to return to the client.",
              "headers": "[optional]
                          `JSON` with each key and value of type string to be returned in the HTTP response."
          }`
    }
```

Example of a generic event source. This event source authenticates the incoming request by checking the header `X-Signature-256`.

```yaml
event_sources:
 organization:
 - name: custom-webhook
   description: Events sent on a custom webhook connected to an external system
   display_name: Custom external webhook
   type: flow-custom-webhook
   setup_instructions: |
     ## Custom webhook
     - You webhook URL is `{{source.trigger_url}}`.
     - Your secret is `{{source.config.parameters.secret}}`.
     - The webhook is triggered when you send a POST request to the URL.
     - The request must have a header `X-Signature-256` with value as `HMAC-SHA256` of the request body using the secret as the key.
   config:
     policy: |
         package rego
         payload_as_string := base64.decode(input.request.body_raw) ## body_raw is a base64 encoded string
         expected_signature := crypto.hmac.sha256(payload_as_string, input.parameters.secret)
         output = {"event": event, "event_key": event_key} {
           input.request.method == "POST"
           expected_signature == input.request.headers["X-Signature-256"]
           event := input.request.body
           event_key := "my-event"
         } else = {"response": response} {
           response := {
             "status_code": 401,
             "body": "Unauthenticated"
           }
         }
     parameters:
       secret: "EnterYourRandomSecretHere"
```

The `event_key` output of the policy can be used to define an automation on the event `custom:event_key`. For example:

```yaml
automations:
  - name: Run on custom webhook
    source: custom-webhook
    event_types:
      - "custom:my-event"
    function: function_1
```

Here, you are creating an event source with the name custom-webhook, and the policy validates that there should be a header `X-Signature-256` with a value of `HMAC-SHA256` of raw request body.

A sample curl command to trigger this event source manually is:

```sh
curl -i -H 'X-Signature-256: f1809d5135917b311644058cf1994c5ff4898ad20dbf6e282c1433e6be4e2fe1' \
-d '{"hello":"world"}' \
https://api.devrev.ai/hidden/dev-orgs/DEV-123/event-source-webhooks/custom/d43fc297-03d7-4cbd-bdf9-044847788306
```

## Timer-based event sources

Timer-based event sources can be created to send events based on intervals and cron schedules. In the following example, you have two event sources, one emits events daily at 12:00am, the other every hour (3600 seconds). In the event payload, you see the JSON field metadata you specified in the event source configuration.

```yaml
event_sources:
  organization:
    - name: daily-timer-source
      description: Timer event source based on Cron expression
      display_name: Timer source
      type: timer-events
      config:
        cron: "0 0 * * *"
        metadata:
          event_key: daily_events

    - name: hourly-events
      description: Timer event source based on interval seconds
      display_name: Timer source
      type: timer-events
      config:
        interval_seconds: 3600
        metadata:
          event_key: hourly_events
```

The automation event type for timer events is `timer.tick`. To initiate an automation based on timer events, use the following syntax in manifest.yaml:

```yaml
automations:
  - name: <name-of-automation>
    source: <timer-event-name>
    event_types:
      - timer.tick
    function: <func-name>
```

The payload contains the `metadata` fields you specified in the event source configuration. For example, `{"event_key": "daily_events"}` for the `daily-timer-source`.

## Email-based event sources

You can create an email-based event source that can be used to write automations on top of emails. For this, a sample of the YAML is shown below:

```
  - name: email-event-source
    description: Event source which emits an event when an email is received.
    display_name: Email events listener
    type:  email-forward
    config:
      allowlist:
        - "test@company.com"
        - "mycompanydomain"
```

The event type of the events emitted by this event source is `email.receive`.

When a snap-in using such an event source is deployed, the instructions show a unique email address. You have to set up forwarding in your original
email inbox or Google Group to this email address. In the example above, if the forwarding address is `v1.abc.xyz@hooks.devrev.ai`, you should set up email
forwarding from `test@company.com` to `v1.abc.xyz@hooks.devrev.ai`.

<Callout intent="note">
  Only emails forwarded from the allowlist of emails/domains are emitted as events. Hence, this event source should be used for email forwarding only, not as a direct mailbox to which anyone can send their emails. Emails received (either directly or by forwarding) from senders who aren't in the allowlist are dropped. There are a few exceptions to this like Google's forwarding confirmation emails.
</Callout>

The allowlist can either contain an email address or an entire domain. Strict matching is done for domains, meaning that subdomains are not included.

<Callout intent="warning">
  The email protocol regarding forwarding is not very well defined. We've tested forwarding from common sources like Gmail, Google Groups, and Outlook Inbox. However, if you're having issues with email forwarding on other providers, feel free to contact us.
</Callout>

#### Payload

Below is a sample payload of the events produced by the email event source:

```json
{
    "emailBody": "test reply\r\n\r\nOn Thu, Sep 7, 2023 at 3:23 PM Test User <test@example.com> wrote:\r\n\r\n> test email body\r\n>\r\n",
    "from": [
        "test@example.com"
    ],
    "to": [
        "test@company.com"
    ],
    "cc": [],
    "bcc": [],
    "htmlBody": "<div dir=\"ltr\"><div>test reply</div><div><br /></div><div class=\"gmail_quote\"><div dir=\"ltr\" class=\"gmail_attr\">On Thu, Sep 7, 2023 at 3:23 PM Test User &lt;<a href=\"mailto:test@example.com\">test@example.com</a>&gt; wrote:<br /></div><blockquote class=\"gmail_quote\" style=\"margin:0px 0px 0px 0.8ex;border-left:1px solid rgb(204,204,204);padding-left:1ex\"><div dir=\"ltr\">test email body<br /></div>\r\n</blockquote></div></div>\r\n",
    "inReplyToId": {
        "stringValues": [
            "jksdnfjnsflkdsfkjaabcdefghiuK8BA@mail.gmail.com"
        ]
    },
    "messageId": "ABCdEfghijklmnopqrstuvwZHL+AB_XYZg@mail.gmail.com",
    "rawBodyartifactId": "don:core:dvrv-us-1:devo/802:artifact/296",
    "referenceIds": {
        "stringValues": [
            "abcdabc123123123@mail.gmail.com"
        ]
    },
    "artifactIds": [
      "don:core:dvrv-us-1:devo/802:artifact/1"
    ],
    "replyTo": {
        "stringValues": [
            "test+123@example.com"
        ]
    },
    "sentOn": "2023-09-07T09:56:37Z",
    "subject": "Re: test email title"
}
```

Below is a brief description of the fields:

* `emailBody`: The plain text body of the email.
* `htmlBody`: The HTML body of the email.
* `from`: List of from email addresses of the email.
* `to`, `cc`, `bcc`: List of recipient email addresses.
* `inReplyToId`: Message ID of the email (if received mail is a reply to some other previous mail).
* `messageId`: Message ID of the received email.
* `rawBodyartifactId`: artifact ID for the raw email (in MIME format) received on the event source. You can use the artifact APIs to download this email if you need to.
* `artifactIds`: artifact IDs for attachments in the email.
* `replyTo`: Reply-To header of the email.
* `sentOn`: Timestamp when email was sent (in UTC).
* `subject`: Subject of the email.