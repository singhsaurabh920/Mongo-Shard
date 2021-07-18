## **Initiate Configuration Server**

 #### Connect to one of the node in cluster

- `docker exec -it config-server-1 mongo`
  
- `mongo --host config-server-1`


#### Initiate replicaSet config

```
 rs.initiate({
    _id: "cfsvr",
    version: 1,
    members: [
        { _id: 0, host : "config-server-1:27017" },
        { _id: 1, host : "config-server-2:27017" },
        { _id: 2, host : "config-server-3:27017" }
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

#### Connect to config server

- `mongo --host cfsvr/config-server-1:27017,config-server-2:27017,config-server-3:27017`
- `mongo  "mongodb://config-server-1:27017,config-server-2:27017,config-server-3:27017/?compressors=disabled&gssapiServiceName=mongodb&replicaSet=cfsvr"`
