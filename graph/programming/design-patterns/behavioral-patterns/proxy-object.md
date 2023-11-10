Proxy object is like a middleware which control the object others are working with. You will get getter and setter functions that in which you can control the behavior of the object.

Generally speaking, a proxy means a stand-in for someone else. Instead of speaking to that person directly, you'll speak to the proxy person who will represent the person you were trying to reach. The same happens in JavaScript: instead of interacting with the target object directly, we'll interact with the Proxy object.
## Example
![[attachments/Pasted image 20231110224059.png]]

## When you should use it
1. Data validation: check whether the caller is updating data properly:
![[attachments/Pasted image 20231110224243.png]]

## When you should not use it
1. Performance-heavy calculations.

## Reflect
JavaScript provides a built-in object called Reflect, which makes it easier for us to manipulate the target object when working with proxies. Instead of accessing properties through obj[prop] or setting properties through obj[prop] = value, we can access or modify properties on the target object through Reflect.get() and Reflect.set(). The methods receive the same arguments as the methods on the handler object.
![[attachments/Pasted image 20231110224420.png]]

## Sources
- Learning patterns book