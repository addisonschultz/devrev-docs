# List Works (POST)

```http
POST https://api.devrev.ai/works.list
Content-Type: application/json
```

Lists a collection of work items.



## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/works.list \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "actual_close_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "created_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "issue": {
    "actual_start_date": {
      "type": "preset",
      "preset_type": "last_n_days",
      "days": 4294967295
    },
    "sla_summary": {
      "target_time": {
        "type": "preset",
        "preset_type": "last_n_days",
        "days": 4294967295
      }
    },
    "target_start_date": {
      "type": "preset",
      "preset_type": "last_n_days",
      "days": 4294967295
    }
  },
  "mode": "after",
  "modified_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "stage": {},
  "staged_info": {},
  "sync_metadata": {
    "last_sync_in": {
      "sync_date": {
        "type": "preset",
        "preset_type": "last_n_days",
        "days": 4294967295
      }
    },
    "last_sync_out": {
      "sync_date": {
        "type": "preset",
        "preset_type": "last_n_days",
        "days": 4294967295
      }
    }
  },
  "target_close_date": {
    "type": "preset",
    "preset_type": "last_n_days",
    "days": 4294967295
  },
  "ticket": {
    "sla_summary": {
      "target_time": {
        "type": "preset",
        "preset_type": "last_n_days",
        "days": 4294967295
      }
    },
    "surveys": {}
  }
}'
```