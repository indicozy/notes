![[attachments/Pasted image 20231101111441.png]]
Webhooks are often referred to as reverse APIs or push APIs because the server sends HTTP requests to the client. We need to pay attention to 3 things when using a webhook:

1. We need to design a proper API for the external service to call.
2. We need to set up proper rules in the API gateway for security reasons.
3. We need to register the correct URL at the external service.

## Sources 
- https://github.com/ByteByteGoHq/system-design-101