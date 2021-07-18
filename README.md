# Mongo Sharding

Sharding is a database mechanism used to manage large dataset. In sharding we can distribute our data to multiple resources which help us to divide our read and writes to different shards. Sharding is not go to approach take it as your last option, It has its own pros and cons. In sharding we can not use transaction and rollback, and we need an extra layer between our application and database a query router which distributes all query's based on key among all shards. Sharding enables at collection level,It does not come by default. We have to enable sharding in desired collection and before that we have to enable sharding at database. When we enable sharding at database level it does not enable sharding at collection level we have to enable manually at database level and collection level as well.Non shared collection R/W goes to default shard. We can add any no of shard as we want.For high availability we can run each shard in replication mode
             ![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-production-architecture.bakedsvg.svg?raw=true)

In sharded collection there is shard-key. This key must be involved in all read and writed operation. Based on this key query router send query to perticular shard. Shard key is very important aspect when we shard any collection. We have to identify shard key very intelligently. We have to specify that key when we enable sharding at any collection. The shard key is either a single indexed field or multiple fields covered by a compound index that determines the distribution of the collection's documents among the cluster's shards.All sharded collections must have an index that supports the shard key. The index can be an index on the shard key or a compound index where the shard key is a prefix of the index.

### Generally there are two types of sharding key
- #### Hashed Sharding
  Hashed sharding uses either a single field hashed index or a compound hashed index as the shard key to partition data across your clusterRanged Sharding
- #### Ranged Sharding
  Range-based sharding involves dividing data into contiguous ranges determined by the shard key values. In this model, documents with "close" shard key values are likely to be in   the same chunk or shard. This allows for efficient queries where reads target documents within a contiguous range. However, both read and write performance may decrease with       poor shard key selection.
              ![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-scatter-gather-query.bakedsvg.svg?raw=true)

