```js
PUT task_casepro
{
  "settings": {
    "number_of_shards": 1,
    "number_of_replicas": 0
  },
  "mappings": {
    "properties": {
      "id": {
        "type": "keyword"
      },
      "book_id": {
        "type": "keyword"
      },
      "book_name": {
        "type": "keyword"
      },
      "company": {
        "type": "keyword"
      },
      "yetai": {
        "type": "keyword"
      },
      "first_level_type": {
        "type": "keyword"
      },
      "second_level_type": {
        "type": "keyword"
      },
      "case_name": {
        "type": "keyword"
      },
      "task_instance_id": {
        "type": "keyword"
      },
      "business_type_id": {
        "type": "keyword"
      },
      "business_type_name": {
        "type": "keyword"
      },
      "gl_month": {
        "type": "integer"
      },
      "tenant_id": {
        "type": "keyword"
      },
      "status": {
        "type": "integer"
      },
      "nc_total": {
        "type": "integer"
      },
      "nc_completed": {
        "type": "integer"
      },
      "miss_total": {
        "type": "integer"
      },
      "miss_completed": {
        "type": "integer"
      },
      "delay_days": {
        "type": "integer"
      },
      "date_created": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "assignee_name": {
        "type": "keyword"
      },
      "workflow_process_id": {
        "type": "keyword"
      },
      "workflow_process_name": {
        "type": "keyword"
      },
      "workflow_node_id": {
        "type": "keyword"
      },
      "workflow_node_name": {
        "type": "keyword"
      },
      "workflow_instance_id": {
        "type": "keyword"
      },
      "workflow_task_id": {
        "type": "keyword"
      },
      "business_data_id": {
        "type": "keyword"
      },
      "workflow_task_info_id": {
        "type": "keyword"
      }
    }
  }
}
```
