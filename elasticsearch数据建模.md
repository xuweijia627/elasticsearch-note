## 创建索引
```js
PUT student
{
  "settings": {
    "number_of_shards": 1,
    "number_of_replicas": 0
  },
  "mappings": {
    "properties": {
      "age": {
        "type": "integer"
      },
      "birthday": {
        "type": "date"
      },
      "class_id": {
        "type": "keyword"
      },
      "gender": {
        "type": "keyword"
      },
      "id": {
        "type": "keyword"
      },
      "name": {
        "type": "text",
        "analyzer": "ik_max_word",       // 中文分词
        "search_analyzer": "ik_smart"
      }
    }
  }
}
```
