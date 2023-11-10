The prototype pattern is a useful way to share properties among many objects of the same type. The prototype is an object that's native to JavaScript, and can be accessed by objects through the prototype chain. The prototype pattern in javascript is more [[graph/programming/design-patterns/structural-patterns/flyweight|flyweight]] pattern than [[graph/programming/design-patterns/creational-patterns/prototype|prototype]].

![[attachments/Pasted image 20231110231850.png]]

The prototype pattern is very powerful when working with objects that should have access to the same properties. Instead of creating a duplicate of the property each time, we can simply add the property to the prototype, since all instances have access to the prototype object.

## Prototyping after creation
Since all instances have access to the prototype, it's easy to add properties to the prototype even after creating the instances. Say that our dogs shouldn't only be able to bark, but they should also be able to play! We can make this possible by adding a play property to the prototype.

![[attachments/Pasted image 20231110232034.png]]

## Creating a subclass
