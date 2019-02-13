
# ELK - ElasticSearch Stack

### cat api

```http
GET /_cat/health?v
GET /_cat/nodes?v
GET /_cat/allocation?v
GET /_cat/nodes?h=ip,port,heapPercent,name
GET /_cat/indices/
GET /_cat/master?v
GET /_cat/recovery?v
GET /_cat/plugins?v&s=component&h=name,component,version,description

DELETE /index_name
DELETE /index_pattern*
```

### list, explain, (fix and) restart shard allocation

```http
GET /_cat/shards?h=index,shard,prirep,state,unassigned.reason  # List UNASSIGNED indexes
GET /_cluster/allocation/explain?pretty                        # Explain UNASSIGNED
POST /_cluster/reroute?retry_failed=true                       # Reindex Failed
```

