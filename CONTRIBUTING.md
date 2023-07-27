# CONTRIBUTING


### 目录说明

```
collection (表目录)
 ├─opendb-*
 │  ├─collection.json (表结构)
 │  ├─data.json (可选初始化数据)
 │  └─package.json (表信息)
 ├─...
database (表分类目录)
 ├─opendb-* (表分类)
 │  ├─db_init.json (关联表)
 │  └─package.json (分类信息)
 ├─...
```

#### collection/opendb-*/collection.json
```
{
  schema: {}, // 参考 JSON Schema 规范
  index: [] // 索引，参考 https://uniapp.dcloud.net.cn/uniCloud/db-index
}
```

#### database/opendb-*/package.json
```
{
  "name": "@opendb/opendb-mall",
  "version": "0.0.1",
  "description": "", // 表分类描述
  "keywords": ["","",""], // 关键字，用于表搜索
  "opendb": {
    "type": "database", // 类别，database 标识数据库
    "title": "电商系统" // 标题
  }
}
```


### [Pull Request 指南](https://gitee.com/help/articles/4128)

> ### 注意：表的字段名，不能使用JavaScript关键字
