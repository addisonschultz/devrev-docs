# Inputs

Inputs are settings for a snap-in that allows behavior customization. They're
scoped to either an organization or a user. Organization-scoped inputs remain
common for the organization, while user-scoped settings need to be set for each
user. Each input's schema maps to field descriptor. Snap-ins don't support inputs
of type `date`, `timestamp` or `array` of `booleans`.
Refer to schema field descriptor example for other supported global types:

```JSON
{
  "description": "string",
  "is_filterable": true,
  "is_pii": true,
  "is_required": true,
  "mfz": {},
  "name": "string",
  "origin": "string",
  "ui": {
    "create_view": {
      "is_hidden": true
    },
    "detail_view": {
      "is_hidden": true
    },
    "display_name": "string",
    "filter_view": {
      "is_hidden": true
    },
    "group_name": "string",
    "is_active_in_detail_view": true,
    "is_bulk_action_enabled": true,
    "is_groupable": true,
    "is_hidden": true,
    "is_hidden_during_create": true,
    "is_read_only": true,
    "is_shown_in_summary": true,
    "is_sortable": true,
    "list_view": {
      "is_hidden": true
    },
    "placeholder": "string",
    "summary_view": {
      "is_hidden": true
    },
    "tooltip": "string"
  },
  "default_value": true
}
```

For example, if an organization input to select a part and a user input to select an array of enums need to be implemented:

```yaml
inputs:
    organization:
        - name: part_picker
          description: Input that chooses a part in the organization
          field_type: id
          id_type:
            - product
            - capability
            - feature
            - enhancement
          is_required: true
          default_value: don:core:dvrv-us-1:devo/XXXX/product:XXXX
          ui:
            display_name: Part Picker
    user:
        - name: enum_list_picker
          description: Input to select multiple enums
          field_type: array
          base_type: enum
          allowed_values:
            - value-1
            - value-2
            - value-3
          is_required: true
          default_value: [value-1]
          ui:
            display_name: Enum List Picker
```