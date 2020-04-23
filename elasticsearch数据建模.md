### 创建索引
```
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
### 存入数据
```
POST student/_doc/6
{
  "name": "大乔",
  "age": 22,
  "birthday":"2009-12-10T10:10:10",
  "gender":"女",
  "class_id":"111"
}
```
### 查最大年龄
```
POST student/_search
{
  "size": 0,
  "aggs": {
    "最大年龄": {
      "max": {
        "field": "age"
      }
    }
  }
}
```
### 按性别分桶
```
POST student/_search
{
  "size": 0,
  "aggs": {
    "gender": {
      "terms": {
        "field": "gender"
      }
    }
  }
}
```
### 查年龄大于30的学生，并按性别分桶
```
POST student/_search
{
  "query": {
    "bool": {
      "filter": {
        "range": {
          "age": {
            "gte": 30
          }
        }
      }
    }
  },
  "aggs": {
    "gender": {
      "terms": {
        "field": "gender"
      }
    }
  }
}
```
### 不同班级中，男女分别有多少
```
POST student/_search
{
  "size": 0,
  "aggs": {
    "班级": {
      "terms": {
        "field": "class_id"
      },
      "aggs": {
        "性别": {
          "terms": {
            "field": "gender"
          }
        }
      }
    }
  }
}
```
### 数据迁移
```
POST _reindex
{
  "source": {
    "index": "student"
  },
  "dest": {
    "index": "student1"
  }
}
GET student1/_search
{
  "query": {
    "bool": {
      "filter": {
        "term": {
          "interest": "yy"
        }
      }
    }
  }
}
POST student1/_search
{
  "size": 0, 
  "query": {
    "bool": {
      "filter": {
        "term": {
          "interest": "yy"
        }
      }
    }
  }, 
  "aggs": {
    "gender": {
      "terms": {
        "field": "gender"
      }
    }
  }
}
```
