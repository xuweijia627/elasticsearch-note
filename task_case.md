```js
PUT task_casepro
{
  "settings": {
    "number_of_shards": 1,
    "number_of_replicas": 0
  },
  "mappings": {
    "properties": {
      "actual_end_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "actual_start_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "assignee_name": {
        "type": "keyword"
      },
      "book_id": {
        "type": "keyword"
      },
      "book_name": {
        "type": "keyword"
      },
      "business_data_id": {
        "type": "keyword"
      },
      "business_type_id": {
        "type": "keyword"
      },
      "business_type_name": {
        "type": "keyword"
      },
      "case_name": {
        "type": "keyword"
      },
      "company": {
        "type": "keyword"
      },
      "date_created": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "date_last_updated": {
        "type": "text",
        "fields": {
          "keyword": {
            "type": "keyword",
            "ignore_above": 256
          }
        }
      },
      "day_diff": {
        "type": "long"
      },
      "delay_days": {
        "type": "integer"
      },
      "first_level_type": {
        "type": "keyword"
      },
      "gl_month": {
        "type": "integer"
      },
      "id": {
        "type": "keyword"
      },
      "minute_diff": {
        "type": "long"
      },
      "miss_completed": {
        "type": "integer"
      },
      "miss_total": {
        "type": "integer"
      },
      "nc_completed": {
        "type": "integer"
      },
      "nc_total": {
        "type": "integer"
      },
      "planned_task_end_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "planned_task_start_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "second_diff": {
        "type": "long"
      },
      "second_level_type": {
        "type": "keyword"
      },
      "spt": {
        "type": "integer"
      },
      "status": {
        "type": "integer"
      },
      "task_instance_id": {
        "type": "keyword"
      },
      "tenant_id": {
        "type": "keyword"
      },
      "workflow_instance_id": {
        "type": "keyword"
      },
      "workflow_node_id": {
        "type": "keyword"
      },
      "workflow_node_name": {
        "type": "keyword"
      },
      "workflow_process_id": {
        "type": "keyword"
      },
      "workflow_process_name": {
        "type": "keyword"
      },
      "workflow_task_id": {
        "type": "keyword"
      },
      "workflow_task_info_id": {
        "type": "keyword"
      },
      "yetai": {
        "type": "keyword"
      }
    }
  }
}
```
