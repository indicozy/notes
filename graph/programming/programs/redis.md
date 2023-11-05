![[attachments/Pasted image 20231105233026.png]]

1. Redis is a RAM-based data store. RAM access is at least 1000 times faster than random disk access.
2. Redis leverages IO multiplexing and single-threaded execution loop for execution efficiency.
3. Redis leverages several efficient lower-level data structures.

## How can Redis be used?
![[attachments/Pasted image 20231105234038.png]]

Redis can be used in a variety of scenarios as shown in the diagram.

- Session
    We can use Redis to share user session data among different services.
- Cache
    We can use Redis to cache objects or pages, especially for hotspot data.
- Distributed lock
    We can use a Redis string to acquire locks among distributed services.
- Counter
    We can count how many likes or how many reads for articles.
- Rate limiter
    We can apply a rate limiter for certain user IPs.
- Global ID generator
    We can use Redis Int for global ID.
- Shopping cart
    We can use Redis Hash to represent key-value pairs in a shopping cart.
- Calculate user retention
    We can use Bitmap to represent the user login daily and calculate user retention.
- Message queue
    We can use List for a message queue.
- Ranking
    We can use ZSet to sort the articles.