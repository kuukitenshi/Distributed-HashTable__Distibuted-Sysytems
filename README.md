# Distributed HashTable

This project was a collaborative effort involving two more students for our ```Distributed Systems``` subject.

Was implemented in ```C language```and its objective was to create a distributed system that allows multiple clients acced synchronously the data from the hashtable, throught RPC. The data is hosted in a server that has fault tolerance due the chain replication.

Thats provided us an opportunity to learn about the ```architecture of a distributed system```, in more detail, about the RPC framework with stub and sketeton to hide complexity using trnasparency, and chain replication model to enable fault tolerance, also syncronization of clients and the manage of this concurence, as well as working with the Zookeper coordination service.

All the functionalities were successfully implemented, and we received a ```perfect score```.

---
## Funcionalities

- A ```hash table``` with multiple funcionalities for manipulate the data stored in it.

- A ```client-server system``` where the client and server comunicates through messages made with a ```protobuf```, wich are sent over the network via TCP.

- Allow ```multiple clients synchronously``` with ```concurrency management``` of threads when accessing shared data structures. In this way, clients make Remote Procedure Calls (RPC) to the server, changing a hash table contained therein.

- Support for ```fault tolerance``` through server state replication, following the ```Chain Replication``` model and using the ```ZooKeeper``` coordination service.

### Note:
All code was checked with valgrind ```not having any memory leaks``` (the only leaks come from the ZooKeeper service).

---
## Compilation and Running

To compile the project and generate the executable, use the following command:
```bash
$ make
```

To clean all the ```object``` and ```executable``` files use:
```bash
$ make clean
```

For execute the binaries from the client and the server, run the following commands:
- ### Server
Where the host has the shape ```<ip >:<port>``` and the IP belongs to the machine that has the ```ZooKeeper``` server and the port is the port of the ```ZooKeeper``.
```bash
$ ./binary/table-server <port> <table size> <host>
```

- ### Client:
Where the IP belongs to the machine that has the ```ZooKeeper``` server and the port is the port of the ```ZooKeeper``.
```bash
$ ./binary/table-client <address>:<port> 
```



