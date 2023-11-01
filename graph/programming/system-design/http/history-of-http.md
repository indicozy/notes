![[attachments/Pasted image 20231101111929.png]]
- HTTP 1.0 was finalized and fully documented in 1996. Every request to the same server requires a separate TCP connection.
    
- HTTP 1.1 was published in 1997. A TCP connection can be left open for reuse (persistent connection), but it doesn’t solve the [[graph/programming/system-design/other/hol-blocking|HOL (head-of-line)]] blocking issue.
    
- HTTP 2.0 was published in 2015. It addresses [[graph/programming/system-design/other/hol-blocking|hol-blocking]] issue through request multiplexing, which eliminates HOL blocking at the application layer, but HOL still exists at the transport (TCP) layer.
    
    As you can see in the diagram, HTTP 2.0 introduced the concept of HTTP “streams”: an abstraction that allows multiplexing different HTTP exchanges onto the same TCP connection. Each stream doesn’t need to be sent in order.
    
- HTTP 3.0 first draft was published in 2020. It is the proposed successor to HTTP 2.0. It uses QUIC instead of TCP for the underlying transport protocol, thus removing HOL blocking in the transport layer.

## Sour