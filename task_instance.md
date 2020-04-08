PUT task_instance
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
      "task_name": {
        "type": "keyword"
      },
      "planned_task_start_date": {
        "type": "date"
      },
      "planned_task_end_date": {
        "type": "date"
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
        "type": "date"
      },
      "actual_task_completed_date": {
        "type": "date"
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
        "type": "date"
      },
      "last_updated_by_user_name": {
        "type": "keyword"
      },
      "is_deleted": {
        "type": "integer"
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
PUT task_instance/_doc/273386176135168002
{
  "id": "273386176135168002",
  "book_id": "33"
}
