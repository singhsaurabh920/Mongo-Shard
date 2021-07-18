## **Initiate Mumbai Region Shard**

#### Connect to one of the node in cluster

- `docker exec -it mumbai-node-1 mongo`

- `mongo --host mumbai-node-1`


####Initiate replicaSet config

```
 rs.initiate({
    _id: "mum",
    version: 1,
    members: [
        { _id: 0, host : "mumbai-node-1:27017" },
        { _id: 1, host : "mumbai-node-2:27017" },
        { _id: 2, host : "mumbai-node-3:27017" }
    ]
})
```

####Check replicaSet status

- `rs.status();`
- `rs.conf();`
- `rs.printReplicationInfo()`
- `rs.printSecondaryReplicationInfo()`

####Add and Remove replicaSet member

- `rs.add(hostname, arbiterOnly)`
- `rs.remove(hostname)`