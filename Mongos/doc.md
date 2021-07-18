## **Initiate Mongo Query Router**
 `docker-compose up -d`
 #### Connect to Mongos
- `mongo --host localhost --port 27017`
- `docker exec -it mongos bash`

#### Enable/Disable sharding

- `sh.enableSharding(database, primaryShard)`
- `sh.shardCollection(namespace, key, unique, options)`
- `sh.reshardCollection(namespace, key, unique, options)`
- `sh.disableBalancing()`
- `sh.enableBalancing()`
- `sh.disableAutoSplit()`
- `sh.enableAutoSplit()`
 #### Add Shards to Mongos
- `sh.addShard("del/delhi-node-1:27017,delhi-node-2:27017,delhi-node-3:27017")`
- `sh.addShard("mum/mumbai-node-1:27017,mumbai-node-2:27017,mumbai-node-3:27017")`
- `sh.addShard("kol/kolkata-node-1:27017,kolkata-node-2:27017,kolkata-node-3:27017")`
#### Check Shard Status
- `sh.status()`
- `sh.balancerCollectionStatus()`
