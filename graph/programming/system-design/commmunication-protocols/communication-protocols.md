- [[graph/programming/system-design/commmunication-protocols/soap|SOAP]]: 
Mature, comprehensive, XML-based
Best for enterprise applications 
- [[graph/programming/system-design/commmunication-protocols/rest|REST]]: 
Popular, easy-to-implement, HTTP methods 
Ideal for web services 
- [[graph/programming/system-design/commmunication-protocols/graphql|GraphQL]]: 
Query language, request specific data 
Reduces network overhead, faster responses 
- [[graph/programming/system-design/commmunication-protocols/grpc|gRPC]]: 
Modern, high-performance, Protocol Buffers 
Suitable for microservices architectures 
- [[graph/programming/system-design/commmunication-protocols/websocket|websocket]]: 
Real-time, bidirectional, persistent connections 
Perfect for low-latency data exchange 
- [[graph/programming/system-design/commmunication-protocols/webhook|Webhook]]: 
Event-driven, HTTP callbacks, asynchronous 
Notifies systems when events occur
## How to improve performance?
![[attachments/Pasted image 20231101111517.png]]
- Pagination
This is a common optimization when the size of the result is large. The results are streaming back to the client to improve the service responsiveness.

- Asynchronous Logging
Synchronous logging deals with the disk for every call and can slow down the system. Asynchronous logging sends logs to a lock-free buffer first and immediately returns. The logs will be flushed to the disk periodically. This significantly reduces the I/O overhead.

- Caching
We can cache frequently accessed data into a cache. The client can query the cache first instead of visiting the database directly. If there is a cache miss, the client can query from the database. Caches like Redis store data in memory, so the data access is much faster than the database.

- Payload Compression
The requests and responses can be compressed using gzip etc so that the transmitted data size is much smaller. This speeds up the upload and download.

- Connection Pool
When accessing resources, we often need to load data from the database. Opening the closing db connections adds significant overhead. So we should connect to the db via a pool of open connections. The connection pool is responsible for managing the connection lifecycle.

## Comparison


![[attachments/Pasted image 20231101112444.png]]

