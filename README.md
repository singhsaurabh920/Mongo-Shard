# Mongo Sharding

#### `Sharding is a database mechanism used to manage large dataset. In sharding we can destribute our data to multiple resources which help us to devide our read andf write to diffrect shards. Sharding is not go to apporoch take it as your last option, It has is our pros and cons. In sharding we can not use transction and rollback and we need a extra layer between our application and database a query router which distributes all querys based on key. Sharding enables at collection lavel is does not comes by default. We have to enable sharding in desired collection and before that we have to enable sharding at database. When we enable sharding at database level is does not enable sharding at collection level we have to enbale mannually at database level and collection level as well.Non shared collection R/W goes to default shard. We can add any no of shard as we want.For high avilbility we can run each shard in replication mode`

![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-production-architecture.bakedsvg.svg?raw=true)


![alt text](https://github.com/v-saurabhsingh/Mongo-Shard/blob/master/sharded-cluster-scatter-gather-query.bakedsvg.svg?raw=true)

