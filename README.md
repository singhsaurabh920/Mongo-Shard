# Mongo Sharding

##### Sharding is a database mechanism used to manage large dataset. In sharding we can distribute our data to multiple resources which help us to divide our read and writes to different shards. Sharding is not go to approach take it as your last option, It has its own pros and cons. In sharding we can not use transaction and rollback, and we need an extra layer between our application and database a query router which distributes all query's based on key among all shards. Sharding enables at collection level,It does not come by default. We have to enable sharding in desired collection and before that we have to enable sharding at database. When we enable sharding at database level it does not enable sharding at collection level we have to enable manually at database level and collection level as well.Non shared collection R/W goes to default shard. We can add any no of shard as we want.For high availability we can run each shard in replication mode

![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-production-architecture.bakedsvg.svg?raw=true)


![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-scatter-gather-query.bakedsvg.svg?raw=true)

