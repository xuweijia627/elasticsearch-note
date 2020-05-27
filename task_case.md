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
      "task_name": {
        "type": "keyword"
      },
      "planned_task_start_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "planned_task_end_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
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
      "actual_task_started_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "actual_task_completed_date": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "task_status": {
        "type": "integer"
      },
      "closing_cycle_type_name": {
        "type": "keyword"
      },
      "closing_cycle_type_id": {
        "type": "keyword"
      },
      "date_last_updated": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "date_created": {
        "type": "date",
        "format": "yyyy-MM-dd HH:mm:ss||yyyy-MM-dd||epoch_millis"
      },
      "last_updated_by_user_name": {
        "type": "keyword"
      },
      "is_deleted": {
        "type": "boolean"
      },
      "serial_no": {
        "type": "keyword"
      },
      "nc_total": {
        "type": "integer"
      },
      "miss_total": {
        "type": "integer"
      },
      "nc_completed": {
        "type": "integer"
      },
      "miss_completed": {
        "type": "integer"
      },
      "comment": {
        "type": "keyword"
      },
      "task_start_mode": {
        "type": "integer"
      }
    }
  }
}
```
