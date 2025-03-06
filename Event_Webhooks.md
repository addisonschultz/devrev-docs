# Event Webhooks

```http
POST https://api.devrev.ai/webhooks.event
Content-Type: application/json
```

Describes a webhook invocation for an event from DevRev to a webhook's
target URL, where the receiving handler must implement the specified
protocol. Note the documented endpoint is for exposition and not
provided by DevRev.




## Response Body

- 200: Success.

## Examples

```shell
curl -X POST https://api.devrev.ai/webhooks.event \
     -H "Authorization: Bearer <token>" \
     -H "Content-Type: application/json" \
     -d '{
  "type": "account_created",
  "account_created": {
    "account": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "account_deleted": {
    "id": "id",
    "old_account": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "account_updated": {
    "account": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    },
    "old_account": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "ai_agent_response": {
    "agent": "agent",
    "error": {
      "error": "blackcurrant...................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................."
    },
    "progress": {
      "skill_executed": {
        "output": {},
        "skill_name": "blackcurrant...................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................."
      },
      "skill_triggered": {
        "args": {},
        "skill_name": "blackcurrant....................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................................",
        "workflow": {
          "id": "id"
        },
        "workflow_run": {
          "id": "id"
        }
      }
    },
    "session": "session",
    "session_object": "session_object"
  },
  "conversation_created": {
    "conversation": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "group": {
        "id": "id"
      },
      "id": "id",
      "members": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "metadata": {},
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "stage": {
        "name": "name"
      }
    }
  },
  "conversation_deleted": {
    "id": "id",
    "old_conversation": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "group": {
        "id": "id"
      },
      "id": "id",
      "members": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "metadata": {},
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "stage": {
        "name": "name"
      }
    }
  },
  "conversation_updated": {
    "conversation": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "group": {
        "id": "id"
      },
      "id": "id",
      "members": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "metadata": {},
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "stage": {
        "name": "name"
      }
    },
    "old_conversation": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "group": {
        "id": "id"
      },
      "id": "id",
      "members": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "metadata": {},
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "stage": {
        "name": "name"
      }
    }
  },
  "dev_user_created": {
    "dev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "state": "active"
    }
  },
  "dev_user_deleted": {
    "id": "id",
    "old_dev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "state": "active"
    }
  },
  "dev_user_updated": {
    "dev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "state": "active"
    },
    "old_dev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "state": "active"
    }
  },
  "group_created": {
    "group": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "group_deleted": {
    "id": "id",
    "old_group": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "group_member_added": {
    "group": {
      "id": "id"
    },
    "member": {
      "type": "dev_user",
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "state": "active"
    }
  },
  "group_member_removed": {
    "group": {
      "id": "id"
    },
    "member": {
      "type": "dev_user",
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "state": "active"
    }
  },
  "group_updated": {
    "group": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    },
    "old_group": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "id": "id",
  "incident_created": {
    "incident": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "impact": {
        "count": {
          "id": 1000000,
          "label": "label",
          "ordinal": 1000000
        }
      },
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "reported_by": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "severity": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "source": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {},
      "title": "title"
    }
  },
  "incident_deleted": {
    "id": "id",
    "old_incident": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "impact": {
        "count": {
          "id": 1000000,
          "label": "label",
          "ordinal": 1000000
        }
      },
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "reported_by": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "severity": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "source": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {},
      "title": "title"
    }
  },
  "incident_updated": {
    "incident": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "impact": {
        "count": {
          "id": 1000000,
          "label": "label",
          "ordinal": 1000000
        }
      },
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "reported_by": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "severity": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "source": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {},
      "title": "title"
    },
    "old_incident": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "impact": {
        "count": {
          "id": 1000000,
          "label": "label",
          "ordinal": 1000000
        }
      },
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "reported_by": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "severity": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "source": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {},
      "title": "title"
    }
  },
  "link_created": {
    "link": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "link_type": "custom_link",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "source": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "target": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      }
    }
  },
  "link_deleted": {
    "id": "id"
  },
  "link_updated": {
    "link": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "link_type": "custom_link",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "source": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "target": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      }
    },
    "old_link": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "link_type": "custom_link",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "source": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "target": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          }
        ]
      }
    }
  },
  "part_created": {
    "part": {
      "type": "capability",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name",
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "part_deleted": {
    "id": "id",
    "old_part": {
      "type": "capability",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name",
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "part_updated": {
    "old_part": {
      "type": "capability",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name",
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    },
    "part": {
      "type": "capability",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name",
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ]
    }
  },
  "question_answer_created": {
    "question_answer": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "status": "archived"
    }
  },
  "question_answer_deleted": {
    "id": "id",
    "old_question_answer": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "status": "archived"
    }
  },
  "question_answer_updated": {
    "old_question_answer": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "status": "archived"
    },
    "question_answer": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "status": "archived"
    }
  },
  "rev_org_created": {
    "rev_org": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "rev_org_deleted": {
    "id": "id",
    "old_rev_org": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "rev_org_updated": {
    "old_rev_org": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    },
    "rev_org": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "rev_user_created": {
    "rev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "rev_org": {
        "type": "rev_org",
        "id": "id"
      },
      "state": "active"
    }
  },
  "rev_user_deleted": {
    "id": "id",
    "old_rev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "rev_org": {
        "type": "rev_org",
        "id": "id"
      },
      "state": "active"
    }
  },
  "rev_user_updated": {
    "old_rev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "rev_org": {
        "type": "rev_org",
        "id": "id"
      },
      "state": "active"
    },
    "rev_user": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "display_picture": {
        "file": {},
        "id": "id"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "rev_org": {
        "type": "rev_org",
        "id": "id"
      },
      "state": "active"
    }
  },
  "sla_tracker_created": {
    "sla_tracker": {
      "applies_to_type": "conversation",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "metric_target_summaries": [
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        },
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        }
      ],
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla": {
        "id": "id",
        "name": "name",
        "sla_type": "external",
        "status": "archived"
      }
    }
  },
  "sla_tracker_deleted": {
    "id": "id"
  },
  "sla_tracker_updated": {
    "old_sla_tracker": {
      "applies_to_type": "conversation",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "metric_target_summaries": [
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        },
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        }
      ],
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla": {
        "id": "id",
        "name": "name",
        "sla_type": "external",
        "status": "archived"
      }
    },
    "sla_tracker": {
      "applies_to_type": "conversation",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "metric_target_summaries": [
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        },
        {
          "metric_definition": {
            "id": "id"
          },
          "org_schedule": {
            "id": "id",
            "status": "archived"
          },
          "stage": "stage"
        }
      ],
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sla": {
        "id": "id",
        "name": "name",
        "sla_type": "external",
        "status": "archived"
      }
    }
  },
  "survey_created": {
    "survey": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "survey_deleted": {
    "id": "id",
    "old_survey": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "survey_response_created": {
    "survey_response": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "recipient": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "response_channel": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      }
    }
  },
  "survey_response_deleted": {
    "id": "id",
    "old_survey_response": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "recipient": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "response_channel": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      }
    }
  },
  "survey_response_updated": {
    "old_survey_response": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "recipient": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "response_channel": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      }
    },
    "survey_response": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "recipient": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "response_channel": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "stage": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      }
    }
  },
  "survey_updated": {
    "old_survey": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    },
    "survey": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      }
    }
  },
  "sync_history_created": {
    "sync_history": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sync_run": {
        "mode": "initial",
        "progress": {
          "state": "completed"
        }
      }
    }
  },
  "sync_history_deleted": {
    "id": "id"
  },
  "sync_history_updated": {
    "old_sync_history": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sync_run": {
        "mode": "initial",
        "progress": {
          "state": "completed"
        }
      }
    },
    "sync_history": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "sync_run": {
        "mode": "initial",
        "progress": {
          "state": "completed"
        }
      }
    }
  },
  "tag_created": {
    "tag": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name"
    }
  },
  "tag_deleted": {
    "id": "id",
    "old_tag": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name"
    }
  },
  "tag_updated": {
    "old_tag": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name"
    },
    "tag": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "name": "name"
    }
  },
  "timeline_entry_created": {
    "entry": {
      "type": "timeline_comment",
      "body_type": "data",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "object": "object",
      "object_display_id": "object_display_id",
      "object_type": "capability",
      "snap_kit_body": {},
      "visibility": "external"
    }
  },
  "timeline_entry_deleted": {
    "id": "id",
    "old_entry": {
      "type": "timeline_comment",
      "body_type": "data",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "object": "object",
      "object_display_id": "object_display_id",
      "object_type": "capability",
      "snap_kit_body": {},
      "visibility": "external"
    }
  },
  "timeline_entry_updated": {
    "entry": {
      "type": "timeline_comment",
      "body_type": "data",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "object": "object",
      "object_display_id": "object_display_id",
      "object_type": "capability",
      "snap_kit_body": {},
      "visibility": "external"
    },
    "old_entry": {
      "type": "timeline_comment",
      "body_type": "data",
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "object": "object",
      "object_display_id": "object_display_id",
      "object_type": "capability",
      "snap_kit_body": {},
      "visibility": "external"
    }
  },
  "verify": {
    "challenge": "challenge"
  },
  "webhook_created": {
    "webhook": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "secret": "secret",
      "status": "active",
      "url": "url"
    }
  },
  "webhook_deleted": {
    "id": "id"
  },
  "webhook_id": "webhook_id",
  "webhook_updated": {
    "webhook": {
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "secret": "secret",
      "status": "active",
      "url": "url"
    }
  },
  "work_created": {
    "work": {
      "type": "issue",
      "applies_to_part": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "priority": "p0",
      "priority_v2": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "sprint": {
        "type": "curated",
        "id": "id",
        "name": "name",
        "state": "active"
      },
      "stage": {
        "name": "name"
      },
      "title": "title"
    }
  },
  "work_deleted": {
    "id": "id",
    "old_work": {
      "type": "issue",
      "applies_to_part": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "priority": "p0",
      "priority_v2": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "sprint": {
        "type": "curated",
        "id": "id",
        "name": "name",
        "state": "active"
      },
      "stage": {
        "name": "name"
      },
      "title": "title"
    }
  },
  "work_fetched": {
    "result": "forbidden"
  },
  "work_updated": {
    "old_work": {
      "type": "issue",
      "applies_to_part": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "priority": "p0",
      "priority_v2": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "sprint": {
        "type": "curated",
        "id": "id",
        "name": "name",
        "state": "active"
      },
      "stage": {
        "name": "name"
      },
      "title": "title"
    },
    "work": {
      "type": "issue",
      "applies_to_part": {
        "type": "capability",
        "id": "id",
        "name": "name",
        "owned_by": [
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          },
          {
            "type": "dev_user",
            "display_picture": {
              "file": {}
            },
            "id": "id",
            "state": "active"
          }
        ]
      },
      "created_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "id": "id",
      "modified_by": {
        "type": "dev_user",
        "display_picture": {
          "file": {},
          "id": "id"
        },
        "id": "id",
        "state": "active"
      },
      "owned_by": [
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        },
        {
          "type": "dev_user",
          "display_picture": {
            "file": {},
            "id": "id"
          },
          "id": "id",
          "state": "active"
        }
      ],
      "priority": "p0",
      "priority_v2": {
        "id": 1000000,
        "label": "label",
        "ordinal": 1000000
      },
      "sla_summary": {
        "org_schedule": {
          "id": "id",
          "status": "archived"
        },
        "sla_tracker": {
          "applies_to_type": "conversation",
          "created_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "id": "id",
          "metric_target_summaries": [
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            },
            {
              "metric_definition": {
                "id": "id"
              },
              "org_schedule": {
                "id": "id",
                "status": "archived"
              },
              "stage": "stage"
            }
          ],
          "modified_by": {
            "type": "dev_user",
            "display_picture": {
              "file": {},
              "id": "id"
            },
            "id": "id",
            "state": "active"
          },
          "sla": {
            "id": "id",
            "name": "name",
            "sla_type": "external",
            "status": "archived"
          }
        },
        "stage": "breached"
      },
      "sla_tracker": {
        "applies_to_type": "conversation",
        "id": "id"
      },
      "sprint": {
        "type": "curated",
        "id": "id",
        "name": "name",
        "state": "active"
      },
      "stage": {
        "name": "name"
      },
      "title": "title"
    }
  }
}'
```