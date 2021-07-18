## **Initiate Delhi Region Shard**

 #### Connect to one of the node in cluster

- `docker exec -it delhi-node-1 mongo`
  
- `mongo --host delhi-node-1`


####Initiate replicaSet config

```
 rs.initiate({
    _id: "del",
    version: 1,
    members: [
        { _id: 0, host : "delhi-node-1:27017" },
        { _id: 1, host : "delhi-node-2:27017" },
        { _id: 2, host : "delhi-node-3:27017" }
    ]
})
```

#### Check replicaSet status

- `rs.status();`
- `rs.conf();`
- `rs.printReplicationInfo()`
- `rs.printSecondaryReplicationInfo()`

#### Add and Remove replicaSet member

- `rs.add(hostname, arbiterOnly)`
- `rs.remove(hostname)`

#### Connect to replicaSet cluster

- `mongo --host del/delhi-node-1:27017,delhi-node-2:27017,delhi-node-3:27017`
- `mongo  "mongodb://delhi-node-1:27017,delhi-node-2:27017,delhi-node-3:27017/?compressors=disabled&gssapiServiceName=mongodb&replicaSet=del"`