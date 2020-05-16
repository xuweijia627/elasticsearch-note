```js
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

PUT task_instance/_doc/273386176135168002
{
  "id": "273386176135168002",
  "book_id": "33"
}

POST task_instancepro/_search
{
  "size": 0, 
  "aggs": {
    "date_last_updated": {
      "max": {
        "field": "date_last_updated"
      }
    }
  }
}

GET task_instance/_search
{
  "query": {
    "bool": {
      "must": [
        {
          "exists": {
            "field": "business_type_name"
          }
        }
      ], 
      "filter": [
          {
          "multi_match":{
                        "type":"best_fields",
                        "query":"银行流水"
                    }
        }  
      ]
    }
  }
}

POST task_instance/_doc/_bulk
{"index":{"_id":"qqq"}}
{"id": "123456","gl_month":"123"}
{"index":{"_id":"www"}}
{"id": "123456","gl_month":"好"}
{"index":{"_id":"eee"}}
{"id": "123456","gl_month":"1234"}
```
### 清除索引下所有数据
```js
POST task_instance/_delete_by_query
{
  "query": { "match_all": {} }
}
```
### 解决索引变为只读状态
```js
PUT _settings
{
  "index": {
    "blocks": {
      "read_only_allow_delete": "false"
    }
  }
}
```
### 按业务类型聚合
```
POST task_instance/_search
{
  "size": 0,
  "aggs": {
    "type": {
      "terms": {
        "field": "first_level_type"
      },
      "aggs": {
        "taskStatistics": {
          "terms": {
            "field": "task_status"
          }
        }
      }
    }
  }
}
```
