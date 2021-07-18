## **Initiate Kolkata Region Shard**

#### Connect to one of the node in cluster

- `docker exec -it kolkata-node-1 mongo`

- `mongo --host kolkata-node-1`


####Initiate replicaSet config

```
 rs.initiate({
    _id: "kol",
    version: 1,
    members: [
        { _id: 0, host : "kolkata-node-1:27017" },
        { _id: 1, host : "kolkata-node-2:27017" },
        { _id: 2, host : "kolkata-node-3:27017" }
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

#### Connect to replicaSet cluster

- `mongo --host kol/kolkata-node-1:27017,kolkata-node-2:27017,kolkata-node-3:27017`
- `mongo  "mongodb://kolkata-node-1:27017,kolkata-node-2:27017,kolkata-node-3:27017/?compressors=disabled&gssapiServiceName=mongodb&replicaSet=kol"`